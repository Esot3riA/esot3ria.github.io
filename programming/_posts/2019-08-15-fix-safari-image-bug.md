---
layout: post
title: React 앱에서 이미지가 계속 로드되는 오류 해결
comments: true
---

오늘 마주한 오류는 다음 짤로 요약할 수 있겠다.

![image-flickering](/assets/img/programming/190815/1.gif)

## 오류 내용
* React를 사용하는 웹 앱에서 발생하는 오류이다.
* state를 변경할 때마다 이미지가 다시 로드되면서 반짝임(flickering) 현상이 일어난다.
결과적으로 state를 바꾸는 매 키보드 입력마다 이미지가 재 로드된다.
* Chrome에서는 정상적으로 동작하나 Safari에서만 발생한다.

이미지가 반짝이는 것도 문제지만, 원래 이미지가 캐싱이 되지 않는다는 듯이 이미지를 계속 다시 로드하는 현상이 일어났다.
결과적으로 매 입력마다 클라이언트에 부하가 걸려서 자원을 많이 잡아먹는 현상이 일어났다.
가장 이상했던 부분은 Chrome에서는 멀쩡히 돌아가는데 Safari에서만 이러한 현상이 발생한다는 것. 

처음 의심했던 사항으로 Virtual DOM에서 이미지 DOM과 state가 제대로 연결되지 않은 것 때문이 아닌가? 라고 생각했다.
하지만 이미지가 반짝일 때도 이미지 컴포넌트의 render() 메서드는 전혀 호출되지 않았다.
React 상의 렌더링 문제일 경우 render() 메서드가 호출되어야 할 텐데 그렇지 않다는 것이 이상했다.

## 오류 해결법
* 이미지 표시를 background-image를 사용하는 div DOM에서 img DOM으로 변경한다.

문제가 꽤 해결되지 않다가 혹시나? 해서 DOM 타입을 background-image를 사용하는 div에서 img로 바꾸어 보았다.
```
// Before
const Picture = styled.div`
    background-image: url(${props => props.restAPIURL + props.imageURL});
    background-size: cover;
    background-repeat: space;
`;
<Picture imageURL={imageURL[0]} restAPIURL={Properties.restAPIURL}/>

// After
const Picture = styled.img`
    width: 100%;
`;
<Picture src={Properties.restAPIURL + imageURL[0]} />
```

그랬더니 반짝임 없이 잘 동작한다. 당연히 Chrome에서도 이상 없이 동작.
원인은 아직도 잘 모르겠다. 브라우저 버그가 아닐까?