---
layout: post
title: 2022 상반기 라인 신입 공채 후기 (코딩테스트/필기테스트/1차면접/2차면접)
image: /assets/img/programming/220620/0.jpeg
---

> 백엔드 개발자는 경험한 트래픽의 규모에 따라 성장하는 경향이 있습니다.
서버가 적은 사용자 규모에서는 문제없이 동작하더라도, 사용자가 급격히 많아지면 꼭 어느 부분에서는 문제가 생기기 마련입니다.
트래픽이 많아졌을 때 병목 현상이 일어날 수 있는 부분을 미리 감지하고 방어적인 코드를 작성할 수 있어야 훌륭한 백엔드 개발자라고 할 수 있습니다.

개발 커뮤니티에서 종종 들었던 말입니다.
저는 아직 큰 규모의 트래픽을 경험해 본 적은 없지만, 그래서 더더욱 라인에서 근무하며 대규모 트래픽을 직접 경험해 보고 싶었습니다.
아시아권에 걸친 국제적 규모의 트래픽을 직접 다루고 훌륭한 동료들과 복잡한 문제를 함께 해결하는 걸 생각하면 가슴이 두근거렸습니다.
저는 이렇게 라인에 가고 싶다는 생각을 한 지 굉장히 오래 되었습니다.
언제부터 이렇게 생각했는지, 너무 오래되어 지금엔 기억도 잘 나지 않습니다.
아마 군 복무 시절 JLPT를 공부할 때 즈음에는 어렴풋이 생각하고 있었을 테니 족히 5년은 되었을 테지요.

작년에도(2021) 이렇게 한껏 부푼 꿈을 안고 라인 공채에 지원해 보았습니다.
자기소개서를 작성하면서도 면접 때를 생각하며 어떻게 제 장점을 어필할지 이리저리 궁리하곤 했어요.
라인에 가고 싶다는 마음만큼은 누구에게도 뒤지지 않으니 분명 면접 때 좋게 봐 주실 거라고 생각했습니다.

하지만..

![1](/assets/img/programming/220620/1.png)

작년엔 면접은커녕 코딩테스트에서 똑 떨어졌습니다.
많이 충격적이었어요. 저는 이것저것 다양한 분야에서 개발을 해 오면서 얘기할 거리를 많이 가지고 있는 개발자라고 생각했는데,
단지 코딩테스트 하나만으로 면접을 볼 자격도 주어지지 않는다니요.

그래도 제가 알고리즘 분야에서 많이 약한 건 사실이었기 때문에 이번 기회에 코딩테스트를 중점적으로 공부하며 취업 준비에 몰두하자고 생각했습니다. 
다음번 공채에는 코딩테스트를 패스하고 면접까진 한 번 가 보는 게 저의 가장 큰 목표였습니다.
가장 가고 싶었던 회사에 면접 한 번 못 보고 다른 회사에 가는 건 너무 억울했거든요.
그렇게 2021년 겨울 내내 PS 문제를 풀고 포트폴리오, 자기소개서 초안을 재작성하며 보냈습니다.

그리고 올해 봄 다시 기회가 찾아왔습니다.

## 서류

![2](/assets/img/programming/220620/2.png)

서류 지원을 위해 라인에서 어떤 포지션으로 일하고 싶은지 희망 직군을 선택해야 했습니다.
저는 라인에서 다루는 대규모 트래픽을 꼭 직접 경험하고 싶었기 때문에 Messaging Server Engineer 직군을 선택하여 지원했습니다.

자기소개서는 총 세 문항으로 길이 제한 없이 자신이 경험한 프로젝트에 대해 서술해야 했습니다.
그런데 자기소개서를 작성할 때 큰 고민이 있었습니다.
가장 열심히 했고 성과가 잘 나왔던 프로젝트가 ML 기술, 특히 NLP 관련 기술을 주로 사용했는데 Messaging Server Engineer 포지션과는 방향성이 많이 달랐거든요. 
특히 예전에 지인 분께 자기소개서 피드백을 요청드렸을 때 JD와 맞지 않는 경험은 쓰지 말라고 했던 기억이 있어서 NLP 프로젝트를 쓸지 말지 굉장히 고민했습니다.

혹여 저를 ML 개발자로 오해하지는 않을까 몇 날 며칠을 고민하다가, 결국 해당 NLP 프로젝트를 자기소개서 문항 하나를 할애하여 아주 깊이 작성했습니다.
만약 얕게 경험했던 백엔드 프로젝트 위주로만 작성한다면 서류 평가 때는 유리하겠지만 정작 면접 때 경쟁력을 갖출 수 없다고 생각했기 때문입니다.
NLP 프로젝트 쪽은 성과도 만족스러웠고 기술적으로 상당히 깊이 파 봤기 때문에 면접 때 깊은 질문이 들어와도 쉽게 대답할 수 있을 것 같았습니다.

이렇게 **자기소개서를 쓸 때는 면접 과정에서 질문받을 걸 생각하며 작성하는 것이 아주 중요합니다**. 자기소개서도 결국 면접 대비 과정이라고 볼 수 있습니다.
SW마에스트로 과정에 지원할 때는 이 사실을 몰라 면접 때 굉장히 당혹스러운 질문을 받고 쩔쩔맸던 기억이 있는데요.
자기소개서 문항을 쓸 때에는 본인이 잘 아는 분야를 작성해야, 즉 나한테 유리한 판을 깔아야 면접 과정에서 깊이 있게 답변할 수 있습니다.
특히 경력직이 아니라 신입 사원을 뽑는 자리였기 때문에 스킬셋이 다른 프로젝트라도 깊이 파고들어 본 경험을 어필해야 유리할 것이라고 생각했습니다.

아래에서 다시 다루겠지만 이 판단이 면접 때 아주 유효하게 작용했습니다.

## 코딩테스트

서류 전형에서 기본 지원자격에 부합하는 지원자는 모두 코딩테스트를 볼 수 있었습니다.
프로그래머스에서 진행되었고 총 6문제를 180분 안에 풀어야 했습니다.

2021년에도 라인 코딩테스트를 봤던 입장에서 감상을 표현하자면 *어? 지난번보단 좀 쉽지 않나?* 였습니다.
6문제 중 3문제는 입출력과 문자열 가공만 할 수 있다면 간단히 해결되는 문제였고,
2문제는 약간의 생각을 요했지만 문제를 꼬아 놓지 않아서 솔루션만 떠올릴 수 있다면 쉽게 해결 가능한 구현(혹은 DFS) 문제였습니다. 
나머지 한 문제는 카카오 공채에서 나올 법한(...) 복잡한 조건이 걸려 있는 구현 문제였습니다.

작년 코딩테스트는 꽤 난이도 있는 문제가 나왔던 것으로 기억하는데, IT기업들의 코딩테스트 난이도가 전체적으로 점점 내려간다는 이야기가 사실이었나 봅니다.
저는 코딩테스트 공부를 나동빈님의 [이것이 취업을 위한 코딩 테스트다](http://www.yes24.com/Product/Goods/91433923) 책으로만 했었는데
해당 책에 나와 있는 알고리즘 정도만 숙지한다면 평이하게 풀어낼 수 있는 수준이었습니다.
복잡한 구현 문제를 제외하고 5솔로 제출했지만 프로그래머스에서 엣지 케이스를 표시해 주지 않아 정확히 몇 솔인지는 지금까지도 잘 모르겠네요.

![3](/assets/img/programming/220620/3.png)

작년에 패배했던 코딩테스트를 무난히 넘겼습니다. 이것만으로도 일단 한 단계 발전했다는 생각이 들었고 이번 기회를 놓치지 않고 라인에 꼭 들어가고 싶었습니다.

## 필기테스트

문제의 필기테스트입니다. 라인의 필기테스트가 정말 어렵다고 소문이 자자한데 아.. 정말 각오를 하고 들어갔는데도 어려웠습니다.
우선 34문제를 90분 안에 풀어야 해서 생각을 깊게 할 여유를 주지 않습니다. 문항도 길어서 읽고 이해하는 데만 2분이 넘게 걸리는 문제도 있었고요.
객관식으로만 나와도 어려울 것 같은데 주관식 문제, 서술형 문제까지 있습니다. 서술형이라고 대학교 시험처럼 길게 쓰다 보니 나중에 시간 여유가 없어서 혼났네요.

대충 25문제 정도를 긴가민가하면서 풀고 시간적 여유가 없어 나머지 문제는 슥 훑어보고 찍다시피 했습니다.
컴퓨터공학 전공 시험과는 비교도 안 되는 난이도에 정신을 못 차리겠더군요.
전공 지식을 갖추고 있는지를 보는 것이 아니라 단순 지식 그 너머에 있는 것들까지 생각해 보았는지를 묻는 문제였습니다.
전공 수업을 더 열심히 들어 놓을걸 하고 살짝 후회가 되면서도 이런 것까지 생각해 보려면 대학원을 가야 하는 게 아닌가 하는 생각이 들었습니다. 

![4](/assets/img/programming/220620/4.png)

다행히 대학원생만 뽑으려는 의도는 아니었는지 필기테스트도 통과할 수 있었습니다.
이 때부터 합격 메일에 조그맣고 귀여운 캐릭터 그림이 있다는 걸 눈치챘습니다.
다른 분들의 합격 후기를 보니 최종 합격 메일에는 헹가래를 받는 캐릭터가 그려져 있다고 하더라구요.
언젠간 그 캐릭터를 볼 수 있는 날이 올까 생각하며 설레는 마음으로 면접을 준비했습니다.

## 1차 면접

라인 면접을 대비하기 위해 후기글을 찾아보니 1차 면접 때는 필기테스트와 마찬가지로 기술적으로 아주 깊은 내용까지 물어본다는 후기가 많았습니다.
첫 질문은 학부에서 배우는 내용으로 시작하나 두 단계, 세 단계 깊이 들어가면서 지원자가 어디까지 알고 있는지 파악하기 위해 답변을 못 할 때까지 물어본다고 하더라구요.
1차 면접을 잘 보기 위해서는 CS 기초를 다지는 게 무엇보다 중요하다고 생각했습니다.

CS 공부를 위해 저도 다른 분들과 마찬가지로 [Technical Interview Guidelines for Beginners](https://github.com/JaeYeopHan/Interview_Question_for_Beginner) 나 
[Backend Interview Questions](https://github.com/ksundong/backend-interview-question) 등의 리포지토리를 보며 공부했습니다.
하지만 리포지토리에 나와 있는 질문들을 그저 읽기만 하는 것으로는 기술적인 깊이를 쌓는 데 한계가 있다고 생각했습니다.
그래서 마치 전공시험 공부를 하듯이 리포지토리에 나와 있는 내용들을 제 나름의 언어로 정리하고자 했습니다.
기본적으로 CS 리포지토리에 나와 있는 질문으로 공부를 시작하되 세부적인 내용들에 대해 끊임없이 질문을 던지며 명확하게 설명할 수 없는 부분을 따로 찾아 공부했습니다.
그리고 공부한 내용이 머릿속에 오래 남도록 Notion에 제 스타일로 따로 요약 정리하여 나중에 쉽게 복습할 수 있게 했습니다.

![5](/assets/img/programming/220620/5.png)

예를 들어 CS 리포지토리에 Spring이 JSP 등의 페이지를 제공하는 원리가 나와 있다면, 조금 더 구체적으로 Spring 내부에서 사용하는 Servlet의 동작 원리는 무엇인지,
Servlet의 라이프사이클은 어떻게 동작하며 `web.xml`이 각 Servlet과 매핑되는 URI를 어떻게 관리하고 `DispatcherServlet` 구조가 `web.xml`을 어떻게 대체하는지 등
더 이상 질문을 던질 수 없을 때까지 DFS 식으로 꼬리에 꼬리를 물며 질문을 정리했습니다.

이 부분은 따로 책으로 공부하기보다는 궁금증이 생겼을 때 구글에 검색하고 여러 페이지를 찾아 보며 지식을 제 것으로 체득하는 것이 더 편했습니다.
좋은 글이라 나중에 참고해야겠다 싶은 링크들만 몇 개 뽑아 따로 즐겨찾기로 정리했는데, 면접 준비 끝날 즈음엔 위 사진처럼 꽤나 많이 쌓였습니다.
저는 이렇게 면접을 준비하면서 이론적으로 모르는 내용들이 아직 한참 많다는 사실을 깨달았습니다. 취준 과정이 끝나더라도 CS 공부는 항상 갈고닦아야 함을 절실히 느꼈습니다.

라인 1차 면접을 볼 때 이렇게 직접 정리한 CS 지식들이 정말 많은 도움이 되었습니다.
CS의 4대 요소라고 할 수 있는 네트워크, 데이터베이스, 자료구조, 운영체제 과목 모두 골고루 돌아가며 심도 깊은 질문이 나왔고 제가 이해했던 내용을 말로 풀어 설명했습니다.

하지만 절대 모든 질문에 대답할 수 있던 것은 아니었습니다. 간단한 질문인데 꼼꼼히 공부하지 않은 부분이라 대답하지 못해 상심했던 경우도 더러 있었습니다.
또한 제가 진행했던 프로젝트에 CS 지식을 접목하여 실무적으로 심도 깊은 내용을 질문받았던 경우도 있었는데요. 이런 질문은 제가 한 번도 생각하지 못한 부분인 경우가 많았습니다.
이렇게 평소에 생각하지 못했던 질문이 나올 경우 잠시 생각할 시간을 주실 수 있는지 양해를 구하고 최대한 아는 지식을 끌어모아 대답하려고 노력했습니다.
이렇게 난해한 질문은 어차피 완벽한 답변을 할 수 없고 면접관 분들도 그걸 기대하는 게 아니라고 생각했기 때문에, 가능한 한 합리적인 추측을 하고 이를 말로 설명하기 위해 최선을 다했습니다.

1차 면접에서 약 50분의 시간동안 30개가 넘는 질문을 받았습니다. 저는 나름 많이 준비했다고 생각했는데.. 중간부터 쉬운 질문에 답변이 막히기 시작하며 멘탈이 흔들렸습니다.
*이걸 내가 왜 모르지? 당연히 공부했어야 하는 내용 아닌가?* 라는 생각이 스멀스멀 피어오르며 저 멀리 날아갈 듯한 멘탈을 부여잡고 어떻게 마지막 인사까지 마쳤는데요.
면접이 끝나고 너무 아쉬운 면접이라고 생각했습니다. 더 잘 할 수 있었는데 하는 생각이 떠나질 않더라구요. 
그래서 1차 면접이 끝나고 답변을 못 한 내용들을 따로 모은 뒤 개인 Notion 정리노트에 최대한 자세하게 정리했습니다. 다른 면접에서는 똑같은 실수를 반복하지 않기 위해서요.

![6](/assets/img/programming/220620/6.png)

거의 반쯤 포기하고 있었는데 기회가 한 번 더 왔습니다.
1차 면접과 같은 실수를 다시는 하지 않으리라 다짐하며 2차 면접을 준비했습니다.

## 2차 면접

보통 네이버나 카카오 등 다른 IT 기업의 2차 면접은 인성 질문 위주인 경우가 많지만 라인의 2차 면접은 기술과 인성 질문이 섞여 있는 형태였습니다. 
라인에서 2차 면접을 칭하는 문장은 다음과 같습니다.

> 기술적인 면과 더불어 조직에서의 fit과 가능성을 확인하는 단계

면접을 준비하는 지원자 입장에서는 굉장히 난해한 문장인데요. 기술 면접을 중심으로 대비해야 할지, 인성 면접을 중심으로 대비해야 할지 전혀 갈피가 잡히지 않았습니다.
구글링을 해 봐도 인성 위주로 질문을 받았다는 분들이 계시는 반면 1차 면접과 같이 대부분 기술 위주로 물어봤다는 분들도 계셨습니다.

제 입장에서는 당연히 둘 다 준비해야 했지만 어느 쪽에 중점을 둘지 선택해야 했고 이번에도 기술 쪽에 초점을 맞추기로 결정했습니다.
2차 면접 전에 인성검사 과정이 포함되어 있었는데 이 단계에서 인성을 어느 정도 검증할 것이라고 생각했기 때문입니다.
또한 1차 면접 때 기술적으로 조금 부족한 모습을 보여드렸기 때문에 기술적인 면에서 추가 질문이 꼭 들어올 것이라고 생각했습니다.

그렇게 1차 면접때보다 더 깊이 CS 공부에 매진했습니다.
그렇다고 인성 질문을 대비하지 않은 것은 아닌데요. 이따금 시간을 내어 제가 진행한 프로젝트를 찬찬히 떠올리며 어떤 이슈가 있었는지, 어떻게 해결했고 여기에 어떤 의미가 있는지 머릿속으로 정리했습니다.
하지만 대부분의 시간을 CS 공부를 하며 보냈고 이번에는 애매하게 알고 있던 내용들을 직접 Java 코드 형태로 작성하고 돌려 보기도 했습니다. 

2차 면접 분위기는 면접관 분들마다 아주 판이하게 다르다고 들었지만, 제가 겪은 바에 따르면 대부분 1차 면접 때와 같이 기술적인 부분에 대해 질문을 주셨습니다.
특히 이번에는 제네럴한 CS 질문에서 시작하지 않고 제가 진행했던 프로젝트에 초점을 맞추어 CS와 연관된 질문을 주셨는데요.
**제가 자기소개서를 작성할 때 NLP 중심의 프로젝트를 작성했던 것이 이 때 아주 큰 도움이 되었습니다**.
머신러닝과 직접적으로 관련된 포지션이 아님에도 불구하고 면접관 분께서 제가 진행한 NLP 프로젝트에 대해 현업에서 겪을만 한 아주 딥한 질문을 주셨습니다.
다행히 현업 프로젝트 중에 제가 한 번 해결해 본 문제들이었기 때문에 최대한 자세하게 대답할 수 있었으며, 특히 수식 관련된 질문까지 성공적으로 대답할 수 있었습니다.

하지만 그럼에도 불구하고 전혀 생각지도 못 했던 질문들도 더러 나왔으며 1차 면접 때와 같이 답을 헤맨 경우도 꽤 있었습니다.
제 경우 1차 면접보다 2차 면접이 기술적으로 훨씬 어려웠고 현업에서 실제 고민해 보지 않았으면 답하지 못 했을 법한 질문들이 주로 나왔습니다.
이렇게 문제들을 깊이 논의하다 보니 60분을 거의 다 썼고 인성 관련 질문은 후반부에 몰아서 조금만 나왔습니다.

잘 답한 것도 있고 애매하게 답한 것도 있어 결과를 확신하기 어려운 상황이었습니다.
특히 다른 지원자 분들 중 인성 중심으로만 물어봤다는 분도 꽤 많이 계셔서, 제가 기술적인 면에서 많이 부족했기 때문에 이렇게 오래 걸렸나 하고 자책하기도 했습니다.
그렇게 2차 면접을 마무리하고 오만 가지 생각이 다 드는 한 주를 보냈던 기억이 있네요.

## 그리고...

![7](/assets/img/programming/220620/7.png)

![8](/assets/img/programming/220620/8.jpg)

밖에서 혼자 규동 먹고 있을 때 최종 합격 메일을 받았는데 손이 떨려서 정말 한동안 젓가락을 못 집었습니다.
헹가래 받는 아저씨 그림을 보는 날을 꿈에 그렸는데 이렇게 현실이 되어 너무 기쁩니다.

제가 합격할 수 있었던 가장 큰 요인은, 물론 CS 공부도 있겠지만, 제가 과거에 내렸던 결정들과 제 행동을 바탕으로 저 본인이 어떤 사람인지 정확히 파악하는 것에서 왔다고 생각합니다. 
제가 다른 사람들과 비교해 어떤 강점을 가지고 있는지 파악하고 면접관에게 차별화된 강점을 정확히 어필할 수 있었기 때문에 이렇게 합격할 수 있었습니다.
기나긴 취준 기간동안 제가 인생에서 내렸던 결정들을 되돌아보며 *나는 보통 사람들과 다르게 이런 결정을 내리고 이런 행동에서 자부심을 느끼는 사람이구나* 하는 깨달음을 얻었습니다.
자기 자신에 대한 확신이 생겼을 때 비로소 면접관에게 저를 뽑아야 하는 이유에 대해 설득력 있는 답변을 할 수 있었습니다.

~~여담입니다만 선택의 중요성을 강조했던 금강선 디렉터님의 말씀을 듣고 에버그레이스 앞에 선 모험가마냥 제가 했던 선택들을 되돌아볼 수 있었습니다. 정말입니다. 그저 감사합니다 금강선 디렉터님~~

![9](/assets/img/programming/220620/9.jpg)

예전에 라인에 정말 가고 싶어서 "나는 LINE 개발자입니다"라는 책을 사서 읽었던 적이 있습니다.
라인에서 일하며 다양한 문제에 부딛히고 훌륭한 동료들과 함께 성장하는 개발자들이 그저 부러웠는데요, 이제야 이 말을 할 수 있겠네요.

저도 LINE 개발자입니다.
