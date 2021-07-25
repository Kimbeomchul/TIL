# 본 문서는 RestAPI를 더욱 Restful하게 작성하기위해 작성됨

### URL Rules
- URL 마지막에는'/'를 붙이지 않는다.
- 언더바(_) 대신 (-) 를 사용한다.
- URL에는 대문자를 사용하지않는다.
- POST/UPDATE/DELETE/GET와 같은 요청은 URL에 포함시키지 말아야한다.
- 컨트롤자원을 의미하는 URL은 예외적으로 동사를 허용한다. (Ex. duplicate)
- URI에 파일의 확장자(예를들어 .json , .JPGE)를 포함 시키지 않습니다.
- URI에 _는 사용하지않는다. 

### Restful 하면 좋은점
- "Restful하다"라는 것은 REST API의 설계가이드에 알맞게 작성되었다는 것이다.
  + Restful하게 작성시 그 자체만으로도 API의 목적이 무엇인지 쉽게 알 수 있다.
  + API를 RESTful 하게 만들어서 API의 목적이 무엇인지 명확하게 하기 위해 RESTful 함을 지향 해야한다.

... 추가예정

이를 지키지않고 그저 만들기에 급급했던 나... 잉생..
