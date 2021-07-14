#Rest

### Rest란
- 자원을 정의하고 자원에 대한 주소를 지정하는 방법론을 의미한다고 한다. 이런 REST의 형식을 따른 시스템을 RESTful 이라고 부른다.
- HTTP URI 를 통해 자원을 명시하고 HTTP Method를 통해 해당 자원의 대한 CRUD Operation을 적용한다.

### CRUD Operation , HTTP Method
1. Create : POST (자원 생성)
2. Read : GET (자원의 정보 조회)
3. Update : PUT (자원의 정보 업데이트)
4. Delete : DELETE (자원 삭제)

### REST 특징
- 클라이언트 / 서버 구조 (Client-Server)
  + 자원이 있는 Server , 자원을 요청하는 Client의 구조를 가진다.
- 무상태 (Stateless)
  + HTTP는 Stateless 프로토콜 이므로 REST 역시 무상태성을 가진다. 클라이언트의 Context 를 서버에 저장하지 않는다.
- 캐시 처리 가능 (Cachealble)
  + 웹 표준 HTTP 프로토콜을 그대로 사용하므로 , 웹에서 사용하는 기존의 인프라를 그대로 활용 가능하다.
- 계층화
  + API 서버는 순수 비즈니스 로직을 수행하고 그 앞단에 사용자 인증 , 암호화 , 로드밸런싱 등을 하는 계층을 추가하여 구조상의 유연성을 줄 수 있다.
- 인터페이스 일관성(Uniform Interface)
  + URI로 지정한 자원에 대한 조작을 통일되고 한정적인 인터페이스로 수행한다. HTTP 표준에만 따른다면 모든 플랫폼에 사용이 가능하다.
- 자체 표현 구조
  + 동사(Method) + 명사(URI) 로 이루어져있어 어떤 메서드에 무슨 행위를 하는지 알 수 있으며 REST API 자체가 매우 쉬워서 API 메세지 자체만 보고도 API를 이해할 수 있다
 
[출처](https://hckcksrl.medium.com/rest%EB%9E%80-c602c3324196)
[예제](https://github.com/Kimbeomchul/Santa)
