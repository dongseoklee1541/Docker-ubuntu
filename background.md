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

* docker container ps -a : 모든 도커 컨테이너들의 정보가 나타남

* docker container rm(prune) webserver : webserver 라는 이름의 컨테이너 모두 삭제 , prune을 쓸경우 정지되어 있는 컨테이너 모두 삭제

