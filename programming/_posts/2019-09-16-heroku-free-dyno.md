---
layout: post
title: 헤로쿠의 Free dyno가 잠자는 것을 막아 봅시다
image: /assets/img/programming/190916/0.png
---

[Heroku](https://www.heroku.com)는 AWS와 비슷한 클라우드 서버 제공 업체로 무료 인스턴스인 Free Dyno를 기본 제공합니다.
이 Free Dyno는 거의 무제한으로 쓸 수 있어서 토이 프로젝트 용으로 아주 유용하지만 30분간 접속이 없을 시에 서버가 내려가는 단점이 있습니다.
한 번 서버가 내려가면 사이트에 접속하기까지 시간이 상당히 걸리는데(지연 시간이 10초는 걸린다), 여러 사람이 사용하기 시작하면 꽤 큰 불편으로 다가옵니다.
이 때 Heroku에서 제공하는 New Relic 애드온을 사용하면 주기적으로 Heroku 서버가 내려가지 않게 막을 수 있습니다.

## New Relic 설치법

![1](/assets/img/programming/190916/1.png)

Heroku 인스턴스가 세팅되어 있다면 바로 [New Relic Addon](https://elements.heroku.com/addons/newrelic)에서 New Relic 애드온을 추가할 수 있습니다.
2019년 9월 기준 무료 플랜인 Wayne을 선택하고, *App to provision to* 부분에서 자신의 Heroku 인스턴스 이름을 검색하여 등록하면 됩니다.

![2](/assets/img/programming/190916/2.png)

Heroku Dashboard에서 인스턴스에 들어가면 애드온 목록에 New Relic APM이 추가된 것을 볼 수 있고, 빨간 원 부분 링크를 클릭하면 New Relic 설정 콘솔로 들어갈 수 있습니다.

![3](/assets/img/programming/190916/3.png)

맨 처음에 Welcome Page가 나오는데 무시하고 메뉴 바에서 SYNTHETICS에 들어갑니다.
New Relic이 모니터링 하기 위한 웹 사이트 주소를 설정하는 메뉴로, 여기에 본인 페이지의 URL 주소를 세팅하면 주기적으로 핑을 쏴 주면서 인스턴스가 내려가지 않게 됩니다.
오른쪽의 Add New를 클릭하여 새로운 모니터링 규칙을 만듭니다.

![4](/assets/img/programming/190916/4.png)

1. *Choose your monitor type*
* 핑을 쏴 주는 것이 목적이므로 Ping을 선택합니다.

2. *Enter the details*
* 모니터링 규칙의 이름과 URL 주소를 명시합니다.
* 이름은 아무렇게나 지어도 되며 URL 주소는 본인의 Heroku 인스턴스의 접속 URL을 입력합니다(ex: `roaring-airpods-12345.herokuapp.com`).

3. *Select monitoring locations*
* Ping을 쏠 리전을 선택합니다. 저는 Seoul, KR로 선택했습니다.

4. *Set the schedule*
* Ping을 쏠 Interval을 설정할 수 있습니다. 30분 Idle 시에 서버가 내려가므로 15분 정도로 설정합니다.

입력이 끝났다면 Create my moniter를 눌러 모니터링 정보를 등록하면 됩니다.
이제 설정이 다 되었고 매 15분 간격으로 Ping이 쏴지면서 서버를 계속 유지시켜 줄 것입니다.

---

사실 New Relic은 모니터링 툴이므로 Heroku 서버가 내려가지 않게 막아 주는 것은 물론
페이지 로드 속도나 페이지 사이즈, 접근성 등에 대한 유용한 정보를 얻을 수 있습니다.
이렇게 한 번 세팅해 두면 사이트 관리 면에서도 도움이 되리라 생각합니다.

**주의:** 신용카드 등록이 되지 않은 계정이거나 2개 이상의 Free Dyno 인스턴스를 운영하는 경우 주의가 필요합니다.
Heroku에서는 Free dyno의 사용 가능 시간을 매달 1천 시간(신용카드 등록이 없는 경우 550시간)으로 제한하고 있으며
Free dyno hours가 전부 소진될 경우 해당 달에는 더 이상 Free dyno를 사용할 수 없습니다.
자세한 정보는 [해당 도움말 링크](https://devcenter.heroku.com/articles/free-dyno-hours)를 참조하세요.
(신용카드가 등록된 계정이 하나의 인스턴스를 24시간 가동하는 것 정도는 괜찮습니다.)
