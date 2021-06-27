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

### 간단명령
- docker stop <이미지id>  => 멈추기
- docker run -d -p 8090:8080 <명명> =>  ( -d : 실행후 터미널로 바로나옴 ) , ( -p 8090:8080 => 포트 080으로설정해놓은 파일을 8090으로 켜지도록 매핑 )

### 효율적인 빌드 
- 좀더 효율적으로 빌드하기위해선 종속성과같은 파일은 따로 COPY를 진행해서 install을 해놓고 이후에 따로 파일들을 COPY해 사용하면 빌드시간이 줄어든다.

### 개발환경 및 운영환경의 Docker 작성
- 보통 개발의 Dockerfile과 운영의 파일이 다르기때문에 구분을 위해 다르게저장함 
  + Ex) 개발 : dockerfile.dev 
  + 하지만 이름을 변경시 docker build가 인식하지 못한다. 해결을 위헤 아래와같은 방법을 사용한다.
    * docker build -f dockerfile.dev . 
    * 이미지를 빌드할때 참조해야할 도커파일을 지정해준다. 



