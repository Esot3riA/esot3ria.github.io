---
layout: post
title: react-scroll-up 라이브러리에 PR을 했습니다
image: /assets/img/programming/201007/0.jpg
---

React에서 Scroll Up 버튼을 만들어 주는 react-scroll-up 라이브러리에 코드 기여를 했습니다.
꽤 오랫동안 꾸준히 사용된 라이브러리인데 Typescript 지원이 아직 안 되어 있어서,
혹시 Typescript를 지원하도록 PR을 해도 되지 않을까? 싶은 마음에 커밋을 만들어서 요청을 넣어 보았습니다.
지금은 PR이 잘 Merge되어 해당 라이브러리가 1.3.4 버전에서 1.3.5로 한 단계 올라간 상태입니다.

원래는 특별히 PR을 할 생각이 없었습니다.
그저 작업 중이던 리액트 프로젝트에 scroll-up 버튼이 필요해서 NPM에서 적당히 라이브러리를 찾은 뒤 끼워넣을 생각이었습니다.
그런데 컴포넌트를 실제로 사용해 보니 이 라이브러리가 Typescript 문법을 지원하지 않는다는 걸 알게 되었습니다.
해당 컴포넌트의 Declaration file을 정의해야 Typescript에서 사용할 수 있었으므로,
긴 삽질 끝에 `index.d.ts` 파일을 만들어 제 프로젝트에서 돌아가게 만들었습니다.

![1](/assets/img/programming/201007/1.jpg)

그런데 react-scroll-up의 Github 리포에 들어가 보니 이미 Typescript 지원에 대한 Issue가 있었습니다.
작년에 나온 이슈였는데 아직까지 해결되지 않은 걸 보니 저와 똑같은 문제를 겪는 사람들이 많이 있을 거라는 생각이 들었습니다.
그래서 이왕 이슈가 있는 거 PR까지 한 번 넣어 보자고 결심했습니다.

![2](/assets/img/programming/201007/2.jpg)

![3](/assets/img/programming/201007/3.jpg)

이슈가 작성된 지 꽤 오래되었으므로 PR을 넣기 전에 이 문제에 대해 다시 언급해야 할 것 같았습니다.
Owner에게 해당 이슈에 대해 PR을 넣어도 되는지 물어보았고 가능하다는 답변을 받아 PR을 요청하였습니다.
그리고 가슴 쫄깃한 리뷰 과정을 거쳐 master 브랜치에 merged되었습니다.

이렇게 react-scroll-up을 Typescript에서 바로 쓸 수 있게 되었습니다.
제 프로젝트에서 불필요한 파일을 하나 뺄 수 있게 된 것도 좋은 점이네요.
정말 간만에 오픈소스 활동을 했는데 나중에 기회가 된다면 또 해 보고 싶습니다.
