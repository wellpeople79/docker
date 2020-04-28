"# docker" 
==========
기본 docker 명령어

1. docker --version 
설치된 도커의 버전을 확인함.

2. docker info 
설치된 도커의 버전을 보다 상세하게 확인함.

3. docker run hello-world: 
도커에서 헬로우 월드(Hello World)를 띄우는 명령어임. 아래처럼 수행됨.

3-1) hello-world라는 이미지를 검색함.

3-2) 로컬에 이미지가 있으면 쓰고, 없으면 도커 허브(Docker Hub)에서 내려받는다.

3-3) 해당 이미지를 컨테이너로 동작시킴.

4. docker-machine stop:
Docker를 종료시킵니다.

5. docker images:
현재 도커 머신에 존재하는 이미지 목록을 출력함.

6. docker ps -a: 
현재 도커 머신에 존재하는 컨테이너를 출력함.

7. docker pull:
image를 다운로드함.

8. docker run:
container 실행함.

9. mysql 실행:
docker run --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=admin -d mysql

10. mysql container에서 mysql shell 실행
docker exec -it mysql bash

mysql -u root -p

11. ubuntu 실행
docker run -it ubuntu /bin/bash

ubuntu 버전확인:
cat /etc/issue


docker root사용자 아닌경우 설정방법
-

  docker가 root 계정으로 설치 되었을때
  
  root 계정이 아닌 계정으로 docker를 실행하면 에러가 발생함.

아래의 명령어 수행 후 재로인하면 사용가능함.
-

$ sudo usermod -a -G docker $USER
$ sudo service docker restart

docker 컨테이너 생성방법
-
  docker run -i -t ubuntu:14.04

-i: 상호입출력

-t: tty 활성화해서 배시(bash) 셸을 사용옵션

컨테어너 내부에서 나가는방법
-
exit, Ctrl + D -> 컨테이너를 나오면서 컨테이너도 정지시킴.

Ctrl + P, Q -> 컨테이너의 셸에서만 빠져나오고 컨테이너는 실행중임.


docker run 오류발생 해결법
---------------------------
docker: failed to register layer: Error processing tar file(exit status 1): write /lib/udev/hwdb.bin: no space left on device.
clean up space by using
docker system prune

Clean your system by removing container and images

$ docker rm $(docker ps -aq)

$ docker rmi $(docker images -q)
