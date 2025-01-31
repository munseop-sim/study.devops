# 컨테이너 격리기술: 컨테이너는 프로세스를 격리시키는 기술이다.
- `docker run -it --rm --name=mycontainer ubuntu:14.04 bash`
    - run : 이미지를 컨테이너로 복제하여 실행
        - `docker run` = `[pull]` + `create` + `start` + `[command]`
    - `-it`: 터미널에 표준입출력으로 명령어 입력
        - `i`: 표준입출력
        - `t`: 터미널할당
    - `--name=mycontainer`: `mycontainer`라는 이름으로 컨테이너 생성
    - `ubuntu:14.04`: `hub.docker.com`에 업로드된 `ubuntu:14.04` 이미지를 대상
    - `bash`: 컨테이너 생성후에 실행시킬 명령어
- 컨테이너 아이디가 UTS namespace(hostname으로 생성됨)
- 컨테이너 라이프사이클
    1. docker 컨테이너는 docker create명령어를 통해 Image의 스냅샷으로 `/var/lib/docker`영역에 생성
    2. docker start 명령어는 읽고 쓰기가 가능한 Process영역. 즉, container layer를 생성하여 동적 컨테이너를 구성하게 된다. 또한 docker stop은 생성된 container layer를 삭제한다.
    3. docker rm은 생성된 snapshot을 삭제하는 과정을 통해 docker container lifecycle을 알 수 있다.
- `/var/lib/docker/overlay2/.../merged`하위에서 실제 도커내부의 파일을 확인 할 수 있다.
    - 해당위치에 파일을 생성하면 도커내부에서도 확인가능하다.