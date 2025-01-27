# 최초 세팅 방법<br/>How to start

1. nginx
   1. localhost:80 포트로 들어오는 모든 경우를 감지 및 포워딩<br/>This container forwards all from localhost:80 to other container.
   2. phpmyadmin ( mysql 편의를 위해 ) 포함.<br/>phpmyadmin container is just for convenient connection.
   3. eg: ㅇㅇㅇ.localhost 로 접속시 ㅇㅇㅇ-httpd-1 컨테이너로 포워딩.<br/>eg: http://ABC.localhost is forwarding to ABC-httpd-1 container.
2. ssh
   1. 터널링같은 ssh 접속이 필요할 경우를 위함.<br/>This container is for something like tunneling.
   2. build/ssh/id_rsa.pub 키파일 필요.<br/>build/ssh/id_rsa.pub is needed
   3. 위 파일은 ssh 접속시 사용할 키로 생성 필요.<br/>The key file is used for connection.
   4. 키파일 없을 경우 생성 방법은 아래 참고.<br/>If you want to make key file please try below.
      1. ssh-keygen -t rsa -b 4096
   5. ssh root@127.0.0.1 -p 20022
3. docker-compose up