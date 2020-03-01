"# docker" 
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
