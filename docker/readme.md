1. [docker 환경설정(local)](config.md)
2. [docker 격리기술](docker_isolation.md)
3. [docker container cli](docker_cotainer_cli.md)


시스템 컨테이너
- centos 설치
- `docker pull centos:7`
- ubuntu 설치
- `docker pull ubuntu`
ctrl + p,q : 컨테이너를 종료시키지 않고 빠져나오기

- 도커 내부 컨테이너의 아이피 확인 : `docker inspect [컨테이너명] | grep -i ipaddress`
- 신규이미지 버전 확인 : `https://hub.docker.com/explore` 접속해서 확인
  - slim, alpine 키워드가 있는 것들이 경량화된 리눅스위에 application 이 돌아간다.
- docker image history [이미지명] 
  - ngnix같은 경우에 어떤 포트가 열려 있는지 확인 가능
  - 그 외에도 해당 이미지에 대한 정보를 확인할 수 있음 


