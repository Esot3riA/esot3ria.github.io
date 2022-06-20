---
layout: post
title: 구름IDE 에디터, 터미널 배경화면 변경하는 방법
image: /assets/img/programming/181202/1.png
---

[구름IDE](https://ide.goorm.io)에도 다른 IDE와 비슷하게 레이아웃의 테마나 배경화면을 변경하는 방법이 존재합니다.
Visual Studio같은 IDE의 경우 테마나 배경화면을 바꾸는 플러그인을 따로 설치해서 변경하곤 하는데,
구름IDE는 웹 기반이기 때문에 화면에 뜨는 **DOM의 CSS를 직접 변경**하는 식으로 커스터마이징이 가능합니다.
표시되는 모든 DOM의 스타일을 변경 가능하기 때문에 자유도가 아주 높아서 온갖 것들이 가능하다는 특징이 있습니다.

## 에디터 배경화면 변경

구름IDE를 커스터마이징 하려면 다음과 같이 하면 됩니다.

![change-goormide-theme-1](/assets/img/programming/181202/2.png)

구름IDE 컨테이너를 실행하고 작업 표시줄의 `구름IDE -> 테마 변경 -> 커스텀 테마 설정`을 선택합니다.
여기에 입력된 코드는 컨테이너 화면 스타일에 그대로 반영되기 때문에 구름IDE 디자이너 마냥 모든 DOM의 스타일을 커스터마이징 할 수 있습니다.
배경화면을 변경하려면 주석 처리된 부분을 풀어서 하나하나 설정하거나 `editor-background` 부분을 다음과 같이 입력합니다.

```css
/* CSS rule for editor background */
.editor-background {
  opacity: 0.2; /* 투명도 취향에 맞게 조절 */
  background-image: url("https://images8.alphacoders.com/900/thumb-1920-900009.jpg"); /* 원하는 이미지 url 입력 */
  background-repeat: space;
  background-position: right;
  background-size: cover;
}
```

![change-goormide-theme-2](/assets/img/programming/181202/3.jpg)

이렇게 넣어 주면 변경된 배경화면으로 피피미와 포푸코와 함께 신나게 코딩할 수 있습니다.
가끔씩 이미지 파일을 제대로 로드할 수 없는 경우가 생기는데, 배경화면이 제대로 로드되지 않는다면 개발자 도구의 콘솔 창을 확인해 보면
파일을 가져올 수 없다는 메시지가 출력되어 있을 것입니다.

![change-goormide-theme-3](/assets/img/programming/181202/4.png)

이 경우 해당 사이트의 [CORS](https://developer.mozilla.org/ko/docs/Web/HTTP/Access_control_CORS)
정책에 의해 리소스 접근이 막혀 있을 수 있기 때문에,
이미지 파일을 접근 가능한 경로로 바꾸고 다시 시도해 보도록 합시다.
특히 네이버 블로그에서 이미지를 가져오려고 할 경우 이런 문제가 발생합니다.

## 터미널 배경화면 변경

위 코드는 컨테이너의 DOM 엘리먼트인 `editor-background`의 스타일을 직접 수정한 것입니다.
이와 마찬가지로 터미널 엘리먼트의 `class`를 찾아서 터미널의 배경화면을 마음대로 변경해 줄 수 있습니다.
터미널 엘리먼트인 `xterm-viewport`의 배경화면을 다음과 같이 변경하면 배경화면에 이미지를 넣을 수 있습니다.

```css
.xterm-viewport  {
  opacity: 0.3;
  background-image: url("https://i.pinimg.com/originals/92/bc/36/92bc3606367c9d7cfcfad3cb4fe561e6.gif"); /* 원하는 이미지 url 입력 */
  background-repeat: no-repeat;
  background-position: right; /* 취향껏 정렬 */
  background-size: contain;
}
```

![change-goormide-theme-4](/assets/img/programming/181202/5.png)

당연히 gif도 문제없이 동작합니다. 역동적으로 움직이는 포푸코를 보고 있으면 저도 모르게 역동적으로 코드를 짜게 되어 좋습니다.
첨언하자면 터미널 배경은 투명한 것이 좋으므로 터미널에 넣을 짤을 찾을 때는 구글 이미지 검색에서 투명 옵션으로 검색하는 것이 좋았습니다.

---

비슷한 방식으로 화면 왼쪽의 프로젝트 탭이나 협업 탭의 화면을 바꿀 수도 있고,
슬라이드 바의 색깔을 바꾸거나 테마 자체를 새로 짜는 등 마개조가 얼마든지 가능합니다.
웹 개발자에게는 구름IDE가 커스터마이징이 가장 자유롭고 간편한 IDE가 아닐까 싶네요 :)
