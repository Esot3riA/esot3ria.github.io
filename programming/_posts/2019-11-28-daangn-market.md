---
layout: post
title: 2019 당근마켓 웹 개발 챌린지 리뷰
image: /assets/img/programming/191128/0.jpg
---

지난 주에 [프로그래머스](https://programmers.co.kr)에서 진행한 당근마켓 웹 개발 챌린지에 도전해 보았다.
이 챌린지는 실제 당근마켓의 블라인드 채용 과정이었으며, 아직은 취업 쪽으로 생각이 없었지만
(졸업까지 아직 3학기나 더 남았으므로), 과제 내용이 상당히 흥미로워서 챌린지에 응시했고 마감 전 제출까지 완료했다.

특이하게 알고리즘 기반의 코딩 테스트 없이 바로 실무 과제를 던져주고 구현 후 제출하라는 방식이었다.
코드를 제출하면 당근마켓 측에서 합불 여부에 관계없이 피드백을 해 준다고도 하더라. 그래서 _에잉ㅎ 딴 건 모르겠고 코드 리뷰나 받아야겠당_ 하고 개발했다.
혼자서 기술을 배우다 보면 코드 퀄리티가 산으로 가는 경우가 많으니 내 코드를 리뷰해 줄 사람이 필요하다는 생각이었다.

구체적으로 내가 이 챌린지에 응시한 이유는 다음 세 가지였다.
* 챌린지에서 요구하는 기술 스택이 React, Express로 본인의 메인 기술 스택과 일치함
* 그 안에 내가 써 보지 못한 기술들도 들어가 있었음 (Typescript와 React Hooks, MobX, Sequelize 등)
* 필드에서 어떤 식으로 React를 사용하는지 알아보고 싶었음

그냥 React를 좀 더 예쁘게 짜고 싶어서 도전해 보았다.

## 프로젝트를 분석하며 생각한 것들
다음은 맨 처음 프로젝트를 분석하면서 들었던 생각들이다.

* 프로젝트 전반적으로 최근 기술들을 잘 융합하여 사용하고 있다는 느낌이 들었다.
React로 짜여진 예제인데도 마치 Spring과도 같이 MVC 패턴을 구현하는 듯한 코드였는데, 꽤 흥미로웠다.
 
* TypeScript가 적용된 프로젝트를 처음 접했다. TypeScript를 사용하니 정적 레벨에서 타입 체크가 되어
디버깅이 쉬워진다는 것이 자연스레 느껴졌다. 파라미터를 받을 때 항상 받을 파라미터의 type을 선언하는 형태의 코드가 추가되는데, 
type을 선언하는 것이 조금 귀찮다고 느껴질 수 있으나 React 프로젝트 버그의 상당수가 타입 불일치, 파라미터 전달 불일치에서 비롯되는 것을 생각하면 충분히 감당할 만 한 수고라고 본다.

* 상태 관리 라이브러리로 Redux 대신 MobX를 사용하고 있었는데, Spring을 하다 온 사람들에게는 러닝 커브가 훨씬 낮겠다 싶었다.
MobX 특유의 Annotation을 적극적으로 사용하는 문법이 Spring과 비슷해서 굉장히 친숙하게 느껴졌다.
개인적인 의견이지만 Redux보다 MobX가 코드 가독성 면에서는 훨씬 낫다고 생각한다.
적어도 MobX는 처음 봤을 때 어느 정도 알아먹게는 생겼기 때문이다.

그리고 분석하는 과정에서 재미있는 코드 몇 개를 발견했는데 아래에 따로 정리해 본다.

## 유저 로그인 여부를 인증하는 React-Router
React-Router로 컴포넌트 라우팅을 할 때, 사용자 로그인 여부를 판단하기 위해 Route 대신 PrivateRoute라는 라우터를 새로 만들어 쓰고 있었다.
다음 코드는 최상위 컴포넌트 App.tsx의 React-Router 부분 코드이다. 
```
// App.tsx
<Router>
    <Switch>
      <Route path={PAGE_PATHS.SIGNIN} component={Login} />
      <Route path={PAGE_PATHS.SIGNUP} component={Singup} />
      <PrivateRoute
        path={`${PAGE_PATHS.PRODUCT}/:id`}
        redirectTo={PAGE_PATHS.SIGNIN}
        component={ProductDetail}
      />
    </Switch>
</Router>
```

그리고 PrivateRoute의 전신은 다음과 같이 구현되어 있다.
```
// PrivateRoute
<Route
  path={path}
  exact={exact}
  render={(props: any) =>
    authStore!.isLoggedIn() ? (
      <Component {...props} />
    ) : (
      <Redirect
        to={redirectTo}
      />
    )
  }
/>
```

render 파라미터에서 authStore에서 로그인 여부를 판단하여,
로그인이 되어 있으면 컴포넌트를 정상적으로 보여주고 비 로그인 시에는 SIGNIN 페이지로 리다이렉트 시킨다.
React에는 Spring의 Interceptor같은 기능이 없어서 어떻게 유저 인증을 하나 싶었는데 상당히 현명한 방법으로 인증을 구현하고 있었다.

## React에서 구현하는 MVC(비스무리한) 패턴

React는 MVC 패턴을 굳이 구현하지 않아도 앱을 동작하도록 만들 수 있으나, 가독성을 위해서는 아무래도 MVC를 구현하는 게 낫다.
당근마켓 목업 프로젝트에서는 Typescript를 사용하여 MVC와 비슷하게, 단계적으로 데이터에 접근하도록 프로젝트를 구성하고 있었다.
예를 들어 DTO는 이런 식으로 하나의 type으로 구성되어 있었다.
```
export type ProductDto = {
  id: number;
  userId: string;
  title: string;
  image: string;
  category: number;
  description: string;
  price: number;
  year: number;
  mileage: number;
  smoking: boolean;
  createdAt: string;
  updatedAt: string;
}
```
이렇게 미리 정의된 DTO를 바탕으로 Backend에 요청한 후 raw 데이터를 받으면, 넘어온 데이터가 DTO 타입과 일치한다고 보장할 수 있다.
즉 DAO에서 정확한 DTO 타입을 넘겨주는 것이 보장되므로, 다음과 같은 DAO를 구성할 수 있다.
```
async getAll(): Promise<ApiResponse<ProductDto[]>> {
    return axios.get(`${API_HOST}/products`);
}
async getCars(filter: FilterDto): Promise<ApiResponse<ProductDto[]>> {
    return axios.post(`${API_HOST}/products/cars`, filter);
}
async getById(id: string): Promise<ApiResponse<ProductDto>> {
    return axios.get(`${API_HOST}/products/${id}`);
}
```
세 메서드 모두 결과로 ProductDto 타입 데이터를 반환한다. 우리가 이미 알고 있는 DAO-DTO 구현체와 동일한 역할을 한다.
이제 Component에서는 DAO에 정의된 메서드를 사용하여 DB에 접근하면 된다.
Component에서 직접 axios 요청을 날리는 것보다 코드 내용이 훨씬 간결해진다.

---

프로젝트 제출 후 2주일 가량 기다려서 코드 리뷰 결과를 받을 수 있었다. 성적이 꽤 처참했으나... 그냥 성장의 기회로 생각하려고 한다.
