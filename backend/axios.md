# Axios 

### Axios란 ?
- Axios는 브라우저, Node.js를 위한 Promise API를 활용하는 HTTP 비동기 통신 라이브러리이다.
- 운영 환경에 따라 브라우저의 XMLHttpRequest 객체 또는 Node.js의 http api 사용
- Http 요청과 응답을 JSON 형태로 자동변환시켜줌 

### Axios 를 이용한 크롤링
- cheerio 라이브러리를 추가로 임포트한뒤, 크롤링진행 
- Puppeteer 와 같은 라이브러리를 이용하지 않을경우 많은 어려움이 존재...
  + Ex ) 자바스크립트로 HTML값을 변경하는 사이트의경우 못불러온다.. 
  + 경험상 해결한 방법으로는 ... 큰사이트의 경우 개발자도구 - > 네트워크에서 js 다 돌아가면서 찾아서 했었당.. 끄적끄적.. 

