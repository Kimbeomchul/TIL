# Docker

### 시작
- 이미지 생성과정

  + 도커이미지 -> 임시컨테이너로 이동 -> 이미지생성 
  + 이후 임시 컨테이너는 삭- 제 

- 연습삼아 도커이미지를 생성하기 ( npm 사용 )
  + FROM node:10
  + COPY package.json ./    => <( npm install을 위해선 package.json파일이필요하다. 임시 컨테이너로 복사 ? )
  + COPY시 여러파일 copy를 하려면 COPY ./ ./ 를 하면 폴더전체를 복사한다. 
  + RUN npm install
  + CMD ["node","main.js]


### PORT 매핑하기
- docker run -p <포트> : 8080 <이미지이름>
  + 도커의 컨테이너에 접속하기 위해서는 브라우저 주소에 작성하는 포트와 컨테이터 포트의 매핑이 필요함.
  + 매핑을 위해서 -p (port) 명령어로 실행을 시켜 매핑run 

### WORKDIR
- 그냥 이미지를 생성시 copy한 파일들과 여러가지 파일들이 혼합되어있다. 이를 해결하기위해 지정이 필요!
  + WORKDIR /the/workdir/path 를 설정해주면 끝~

  ### Docker 사용 자동화 프로젝트
  - Node.js / AWS / 젠킨스?(미정) .... 
