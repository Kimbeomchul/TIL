# Docker_basic

### 시작
- 도커 이미지 (프로그램을 실행하는데 필요한 설정이나 종속을 가짐)
- 도커 컨테이너 (이미지의 인스턴스이며, 프로그램을 실행한다)
- 도커 이미지 -> 도커 컨테이너
- 도커 Client(CLI) -> 도커 Server(데몬)
- 명령어 실행 -> 도커 클라이언트 -> 도커 서버 -> 실행한 명령어의 이미지가 있는지 확인한 후
없으면 이미지들을 보관하고 있는 도커허브에서 가져온다.

### 사용법
1. 도커 CLI에 커맨드를 입력 ex) docker run hello-world
2. 도커 서버가 커맨드를 받아 그것에 따라 작업을한다~

### 명령어
- 도커 클라이언트 / 명령어 / 컨테이너를 위한 이미지 / 여기 명령어는  이미지가 가진 시작명령어를 무시하고 커맨드를 실행하게 한다.
  +  Ex) docker / run / ** / ls  <여기서 ls 커맨드는 현재 디렉토리의 파일 리스트 표출>
  +  ls 의 명령어의 경우 alpine과 같은 ls를 실행할 수 있는 이미지만 사용가능.

- 도커 상태보기 
  + docker ps  < 현재 실행중인 상태 >
  + Ex ) docker ps --format 'table{{.Names}} \t table{{.Image}}'
  + docker ps -a < 모든 컨테이너를 나열 >

### 도커 생명주기
- 생성(create) -> 시작(start) -> 실행(running) -> 중지(stopped) -> 삭제(deleted)
  + docker create <이미지 이름> // 생성
  + docker start -a <컨테이너 아이디/이름> // 시작 (-a는 attach 화면에 표출해주는 효과)
  + docker stop || docker kill // Stop은 정리할 시간을 주고나서 중지, kill은 바로중지 
  + docker rm <아이디/이름> // 삭제
  
- 모든 컨테이너를 삭제하고 싶을때!
  + docker rm `docker ps -a -q`  <작은 따옴표가아닌 백틱을 이용해야한다 (키보드 1옆에있는것!)>
- 이미지를 삭제하고싶을때 
  + docker rmi <이미지 id>
- 도커의 컨테이너, 이미지 , 네트워크를 모두 삭제하고싶을땐
  + docker system prune (실행중인 것에는 효과x)
- 실행중인 컨테이너에 명령어 전달 
  + docker exec <컨테이너 아이디> <명령어>


### 슬기로운...? 터미널 생활
- docker exec ....를 계속써야할 경우
- docker exec -it <~~> sh (sh -> 쉘환경) 으로 들어가서 명령어를 입력할 수 있다.


### 도커파일 생성법
1. 베이스 이미지를 명시한다. ( 파일 스냅샷 ) < 베이스이미지는 OS라 생각해도됨 > 
2. 추가적으로 필요한 파일을 다운받기 위한 명령어들을 명시한다. ( 파일 스냅샷 )
3. 컨테이너 시작시 실행 될 명령어를 명시한다. ( 시작시 실행될 명령어 )
- From <이미지이름>:<태그> 태그작성을 안하면 자동으로 최신버전으로 다운
- 예시는 같은 깃폴더의 dockerfile 폴더에 있당
  + 도커 빌드시 네이밍법 (docker build -t <도커아이디>/저장소 및 프로젝트이름:버전 ./
  + -t 는 tag~ 


  

- 이미지가 생성되는 순서
![image](https://user-images.githubusercontent.com/54543148/123268887-6a683b00-d539-11eb-92b6-e01b1017ddc0.png)



# Redis를 이용한 Docker 이해 
- docker run redis -> 실행시 해당 터미널은 사용불가(다른 터미널 이용시 같은 컨테이너가 아니다.)
- 해결법 -> docker exec -it <컨테이너 아이디> <명령어> 를이용하여 해결한다
- docker exec -it ~~~~ redis-cli  
    + -it란 iteractive terminal로 명령어 실행 후 계속해서 명령어를 적을 수 있는 환경을 준다.

