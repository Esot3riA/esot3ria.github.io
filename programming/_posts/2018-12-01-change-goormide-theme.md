---
layout: post
title: 구름IDE 배경화면, 테마 변경하는 방법
---

[구름IDE](https://ide.goorm.io)에도 다른 IDE와 비슷하게 레이아웃의 테마나 배경화면을 변경하는 방법이 존재한다.
Visual Studio같은 IDE의 경우 테마나 배경화면을 바꾸는 플러그인을 따로 설치해서 변경하곤 하는데,
구름IDE는 웹 기반이기 때문에 화면에 뜨는 **DOM의 CSS를 직접 변경**하는 식으로 커스터마이징이 가능하다.
표시되는 모든 DOM의 스타일을 변경 가능하기 때문에 자유도가 아주 높아서 온갖 것들이 가능하다는 특징이 있다.

구름IDE의 DOM 스타일을 변경하려면 다음과 같이 하면 된다.

![change-goormide-theme-1](/assets/img/change-goormide-theme-1.png)

구름IDE 컨테이너를 실행하고 작업 표시줄의 `구름IDE -> 테마 변경 -> 커스텀 테마 설정`을 선택한다.
