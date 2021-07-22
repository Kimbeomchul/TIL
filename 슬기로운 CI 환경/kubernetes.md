# Kubernetes

### 쿠버네티스란?
![image](https://user-images.githubusercontent.com/54543148/126629932-bb23519e-53d1-47e8-935d-08a2949f9c39.png)
- 단일  서버에서는 도커의 간단한 명령어로 컨테이너를 만들어서 사용에 어렵지않다. 하지만 두 개 이상의 서버에서 도커 데몬을 이용하면 어떤 시스템에 컨테이너를 생성해야 맞는건지 생각해봐야 한다. 
이런경우 idle상태인 서버에 컨테이너를 생성하여 운영해야한다. 하지만 이럴경우 일일이 idle상태인지 일일이 확인하면서 유지하면 자원이 낭비되기 때문에 사용하는 것이 쿠버네티스와 같은 오케스트레이션 툴이다.


### 오케스트레이션이란 ?
- 오케스트레이션은 컴퓨터 시스템과 애플리케이션, 서비스의 자동화된 설정, 관리, 조정을 의미합니다. 오케스트레이션은 IT 팀이 복잡한 태스크와 워크플로우를 보다 쉽게 관리할 수 있도록 돕습니다.
- [출처_RedHat](https://www.redhat.com/ko/topics/automation/what-is-orchestration)


### 특징
- 로드밸런싱 제공 
  + container1 -> container2 -> container3 순서로 접근할 수 있도록 round-robin형태의 로드밸런싱이 제공된다.
- [이외의 여러가지 특징](https://www.leafcats.com/305)
