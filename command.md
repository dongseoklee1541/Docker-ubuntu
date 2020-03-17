On-premises : 서버실을 직접 사내에 운영하는 경우, 인트라넷

Cloud Platform : 서버를 외주로 사용(AWS, GCP, KT, etc..)

Orchestration : 여러 서버를 관리해주는 것


---

## Docker Terms

* Docker Engine(Docker Daemon, Core): 자동차의 엔진과 같이 도커의 전체적인 운영을 담당

* Docker Machine : 컨테이너들, Host OS(보통 wnidows) 위에서 실행되고 있는 리눅스 서버, MY SQL 서버 등,,

* Dokcer Compose : Docker Machine들을 관리해주는 녀석

* namespace : dict의 key values 값으로 정의가 되있는 상태,

* docker NIC(Network Interface Controller) : 별도의 네트워크로 운영(분리됨)



----

## Docker command

* docker container run <docker-image-name> <command>
  
* docker system df : 도커의 현재 이미지 개수, 사용량 등의 정보를 보여줌

* docker container run -it --name webserver -d -p 80:80 nginx /bin : -it(인풋을 받겠다, 커멘드 가능) 컨테이너의 이름이 webserver , -d 백그라운드로 돌리겠다. -p(포트 번호 나온다) , /bin : 마지막에 들어가는 것은 명령어, 이걸 수행해라
  * i : Interactive 모드로 표준입력과 표준출력을 키보드와 화면을 통해 가능하도록 하는 옵션이다.
  * t:  텍스트 기반의 터미널(TTY)을 애뮬레이션해주는 옵션이다.

* docker (container) ps -a or docker container ls -a : 모든 도커 컨테이너들의 정보가 나타남

* docker container rm(prune) webserver : webserver 라는 이름의 컨테이너 모두 삭제 , prune을 쓸경우 정지되어 있는 컨테이너 모두 삭제

* Ctrl + p , Ctrl + q : 컨테이너를 실행하고, 커멘드 창이 떠있는 상태에서 컨테이너를 종료하지 않고 나올 수 있는 방법(**detach**)

* docker attach <container-name> : detach 로 나온 컨테이너에 다시 재진입

* exit(Ctrl + D) : 도커의 컨테이너를 죽이는 것, 종료하면서 나온다

#### 도커 중지,재실행,명령어
* docker (container) stop <container-name> : 실행되고 있는 컨테이너를 완전히 죽이는 키워드(**stop**)
  
* docker (container) start <container-name> : 종료시킨 컨테이너를 다시 재실행
  
* docker container exec -it <container-name> cat /etc/hosts : 실행되어 있는 컨테이너에게 명령을 주는 커맨드 **exec**
  
----

* docker container port <container-name> : 컨테이너가 사용하고 있는 포트를 알려줌
  
* docker container rename <container-name> <바꿀 이름> : 기존 컨테이너의 이름을 바꾸는 명령어
  
* docker --link : Docker 컨테이너가 다른 컨테이너에 엑세스 할 수있도록 한다.

#### 모든 도커 컨테이너/이미지 삭제

* docker stop $(docker ps -a -q)
* docker rm $(docker ps -a -q)

* docker rmi $(docker images -q) : 모든 도커 이미지 삭제

## 컨테이너 둘러보기
* docker logs [OPTIONS] CONTAINER : 특정 컨테이너가 실행된 후 로그를 보기 위한 명령어
  * OPTIONS 으로 -f, -tail가 있다.
  * -tail n : 마지막 n 줄만 출력해라. ex) docker logs -tail 10 CONTAINER(마지막 10줄만 출력)
  * -f : 실시간 로그 출력
  
## FILE Copy & Share

* docker container cp <container-name>:<path> <client-path> : path(컨테이너의)에 있는 파일을 내 path로 보내
  * docker container cp <client-file> <container-name>:<path> : 내 path에 있는 파일을 컨테이너의 pathd에 보내
  
### Share Directory

* docker run **-v** <localpath>:<container-path> : localpath와 container-path를 연결함, 디렉토리 공유
  
#### in 리눅스

* docker stop `docker ps -q` : 실행 되어 있는 모든 컨테이너를 중지시켜라.
  * docker ps -q : 리눅스 명령어로, 실행되어 있는 컨테이너들의 ID를 보여줌

----

#### install MYSQL

docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root1! --name mysql5 mysql

* -e : 환경변수, os에서 사용하는 변수를 뜻한다.
* MYSQL_ROOT_PASSWORD : ROOT(최고관리자)의 패스워드
