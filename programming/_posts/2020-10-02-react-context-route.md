---
layout: post
title: (React+Typescript) React-Router에서 Context Provider 사용하기
image: /assets/img/programming/201002/0.jpg
comments: true
---

오늘 해결한 이슈는 react-router와 Context API를 적절히 섞는 방법에 관한 문제였다.
react-router의 Route를 사용하여 URI 기반으로 컴포넌트를 표시할 때 보통 Provider를 같이 제공해 줘야 한다.
특히 Context API와 같이 사용할 때, 컴포넌트가 Context를 가지는 경우에 State를 관리하려면 Provider로 한 번 감싸 줘야 한다.
그런데 Route 컴포넌트를 바로 Provider로 묶어 버리면 제대로 라우팅이 되지 않는다.

예를 들어, 기존에 Context 없이 다음과 같이 라우팅을 했다고 하자.

~~~~jsx
// App.tsx
<BrowserRouter>
  <Switch>
    <Route path="/" exact component={Landing} />
    <Route path="/event_detail" component={EventDetail} />        
    <Route path="/notice" component={Notice} />
    <Redirect path="*" to="/" />
  </Switch>
</BrowserRouter>
~~~~

URI에 따라 각각 _Landing_, _Eventdetail_, _Notice_ 컴포넌트를 반환하는 라우터다.
그런데 여기에서 _EventDetail_, _Notice_ 각각의 컴포넌트에 Context가 부여되어야 한다면?
즉 Context API의 Provider를 한 번 거쳐야 한다면 어떻게 해야 할까?

~~~~jsx
// App.tsx
<BrowserRouter>
  <Switch>
    <Route path="/" exact component={Landing} />

    <EventDetailProvider>
      <Route path="/event_detail" component={EventDetail} />
    </EventDetailProvider>
    <NoticeProvider>        
      <Route path="/notice" component={Notice} />
    </NoticeProvider>

    <Redirect path="*" to="/" />
  </Switch>
</BrowserRouter>
~~~~

간단하게 이렇게 각각의 Route를 감싸는 방법을 생각할 수 있다. 하지만 이렇게 감싸면 Route가 제대로 동작하지 않는다.
그 이유는 [\<Switch\>의 자식은 오직 \<Route\>와 \<Redirect\>만 허용되기 때문](https://stackoverflow.com/questions/50155909/how-to-use-context-api-with-react-router-v4/50158702)이다.
즉 Switch-Provider-Route 구조가 아닌 Switch-Route-Provider 구조로 작성해야 제대로 라우팅을 할 수 있다.

그러니까 Provider 안에 Route를 넣지 말고, 아래와 같이 Route 안에 Provider를 넣으면 된다.

~~~~jsx
// App.tsx
<BrowserRouter>
  <Switch>
    <Route path="/" exact component={Landing} />
    
    <Route path="/event_detail">
      <EventDetailProvider>
        <EventDetail />
      </EventDetailProvider>
    </Route>
    <Route path="/notice">
        <NoticeProvider>        
          <Notice />
        </NoticeProvider>
    </Route>

    <Redirect path="*" to="/" />
  </Switch>
</BrowserRouter>
~~~~

Route에 직접 Component를 전달하지 않고 풀어서 작성할 수 있으므로,
내부에 명시적으로 Route-Provider-Component 구조를 작성해 주면 된다.

그런데 이렇게 일일히 Route-Provider-Component를 작성하게 되면 코드가 길어져 가독성이 상당히 떨어질 수 있다.
따라서 내부에 Provider를 포함해 주는 **Context Router**를 Typescript 버전으로 다음과 같이 작성할 수 있다.

~~~~typescript
// ContextRoute.tsx
type ContextRouterProps = {
  path: string;
  exact: boolean;
  Provider: any;
  Component: any;
}

const ContextRoute = (props: ContextRouterProps) => {
  const { Provider, Component } = props;

  return (
    <Route path={props.path} exact={props.exact}>
      <Provider>
        <Component />
      </Provider>
    </Route>
  );
}

export default ContextRoute;
~~~~

이렇게 Provider와 Component를 props로 받고 순서대로 Route-Provider-Component 구조를 만들어 주면, 라우터를 아래와 같이 깔끔하게 작성할 수 있다.

~~~~jsx
// App.tsx
<BrowserRouter>
  <Switch>
    <Route path="/" exact component={Landing} />
    <ContextRoute path="/event_detail" exact Provider={EventDetailProvider} Component={EventDetail} />
    <ContextRoute path="/notice" exact Provider={NoticeProvider} Component={Notice} />
    <Redirect path="*" to="/" />
  </Switch>
</BrowserRouter>
~~~~

기존 Route를 사용하듯이 ContextRoute도 동일한 맥락으로 사용할 수 있다.
이렇게 Provider를 제공하는 Router 외에도 유저 자동 인증을 해 주는 Router 등 여러가지로 응용할 수 있겠다.
