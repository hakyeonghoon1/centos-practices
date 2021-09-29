# mariadb 계정 생성

1-1. database 생성

MariaDB [none]> create database webdb;

1-2. user 생성

MariaDB [none]> create user 'webdb'@'localhost' identified by 'webdb';

1.-3. 권한 부여
MariaDB [none]> grant all privileges on webdb.* to 'webdb'@'localhost';

1-4. 새 변경사항 적용
MariaDB [none]> flush privileges;

1-5. 테스트

mysql -u webdb -D webdb -p

================================================================

워크벤치 연결 계정 생성

2-1. user 생성
MariaDB [none]> create user 'webdb'@'windowip' identified by 'webdb';

*브릿지 연결시 : windowip = 접속할 윈도우 ip

*NAT 연결시 :  127.0.0.1

포트 포워딩 port = 3306

2-2. 권한 부여
MariaDB [none]> grant all privileges on webdb.* to 'webdb'@'windowip';

2-3. 새 변경사항 적용
MariaDB [none]> flush privileges;

2-4. window 워크벤치 새연결

*브릿지 연결 hostname : 리눅스 ip주소 , port : 3306

*NAT 연결 hostname : 127.0.0.1 , port : 3306