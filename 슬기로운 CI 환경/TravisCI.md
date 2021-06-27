# Travis CI

### Travis CI란?
- [공식주소](https://travis-ci.org/)
- Github에서 진행되는 오픈소스 프로젝트를 위한 지속적인 통합 서비스이다. 깃헙에서 개발하고있는 소스를 
특정 이벤트에따라 자동으로 테스트가 가능하며, 빌드하거나 배포또한 할 수 있다.
- 이전에 사용했던 젠킨스와 비슷한느낌인듯하다 ?

### 사용법
- 상단의 공식주소에 접속하여 자신의 깃헙아이디로 로그인한다.
- 오른쪽상단의 계정을 클릭하여 Settings-repository 로 이동하여 활성화 시키고싶은 repository의 radio btn을 활성화한다.
- 이후 상단바의 Dashboard로 이동한 뒤에 해당 repository에 Push를 한번더하면 보인당~
  + 이용하기위해선 .travis.yml를 작성해야한다.

### .travis.yml 작성법
- sudo:    => 관리자 권한을 갖는다. ( required )
- language: => 언어/플랫폼 선택
- services:  =>  Ex)docker
- before_install: => 스크립트를 실행할 수 있는환경을 구성
- script: => 실행할 스크립트
- after_success: => 테스트 성공 후 할일 