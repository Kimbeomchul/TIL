# Docker Compose

### Docker Compose란
- 멀티컨테이너 상황에서 쉽게 네트워크를 연결시켜 주기 위해 이용
  + Ex) Redis서버와 연결이 필요할시

### Ex구성도 ( Redis )
- version : <docker compose 버전>
- services : <실행하려는 컨터이너들 작성>
  + redis-server: <컨테이너 이름>
    * image: <컨테이너에서 사용하는 이미지 이름>
  + <컨테이너 이름>
    * build: < . 이용시 현재폴더에 있는 Dockerfile 사용 >
    * ports: <포트매핑 이전에 사용하던 -p 8090:8080 같은것 >

### 사용법
- docker-compose.yml 파일을 생성
- 상단의 구성도에따라 작성

### 명령어 < docker-compose 명령어는 도커컴포즈 파일이 있는 폴더에서 진행해야한다. >
- docker-compose up
  + 실행하는 컨테이너들을 모두실행
- docker-compose down
  + docker-compose 에 실행된 모든 컨테이너 한번에중지

- docker compose -d up 
  + detached 모드로 앱을 백그라운드에서 실행시킴 ( 오류떠서 실행못했는데 안나와서 당황... )
- docker-compose up --build
  + 이미지가 있던없던 이미지를 빌드하고 실행 / --build가 없는명령어는 이미지가 없을때만 이미지빌드
  