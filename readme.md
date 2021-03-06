
*192 나 10 으로 시작하는건  사설 ip

## 1.  ping
ping 명령을 이용하면 다름 시스템의 네트워크가 현재 동작 중인지 알 수가 있다.

사용법
ping [옵션] 호스트

- 옵션

-s : 패킷 사이즈를 지정한다.

-q : 종합 결과만 보여준다.

-i  : 지연시간을 설정한다.

-c : 보낼 패킷 수를 지정해 준다.

	ping -s 1000 -c 5 www.google.com


ping 응답 설정 여부 확인

	cat /proc/sys/net/ipv4/icmp_echo_ignore_all 

ping 응답을 막는 설정하기 위해 vi /etc/sysctl.conf를 열고 다음을 추가 한다

	net.ipv4.icmp_echo_ignore_all=1


## 2.  nslookup
nslookup은 도메인 네임서버에 질의를 할 수 있는 명령어 이다. 도메인 이름의 호스트의 IP주소를 검색할 수 있고 네임서버가 올바르게 작동하는 지 확인 할 수도 있다.

- 사용법
nslookup [도메인]

도메인을 입력하지 않으면 대화형으로 프로그램이 작동한다.


## 3.  hostname
호스트네임을 화면에 출력하고, 호스트네임을 변경할 수 있다.

- 사용법

hostname

호스트 명 변경
/etc/hostname 파일을 vi 에디터로 열고 수정한다.
저장하고 반영하기 위해 재부팅 한다.


## 4. netstat
네트워크 연결, 라우팅 테이블, 네트워크 장치의 통계정보 등 네트워크에 관련된 여러가지 정보를 확인할 수 있다.

- 사용법
netstat [옵션]

- 옵션

-a : 연결된 모든 소켓을 출력한다.

-n : 호스트, 포트등의 정보를 이름대신 숫자로 표시한다.

-p : 소켓을 열고 있는 프로세스의 아이디(PID) 를 출력한다.

-r  : 라우팅 테이블을 출력한다.

-t  : TCP 연결에 대한 소켓을 출력한다.

-u : UDP 연결에 대한 소켓을 출력한다.

현재 열려 있는 TCP 포트 정보

	netstat -ant | grep LISTEN


현재 열려 있는 TCP 포트의 프로세스까지 출력

	netstat -anpt | grep LISTEN



- 쉘에서 서버다운후 다시 실행 실습

shell에서 

	ifconfig enp0s3  : 가상환경 서버 
	ifconfig down

centos에서 

	cd /etc/sysconfig/network-scripts/
	ifconfig enp0s3 up


## 6.  네트워크 설정하기 (고정 아이피 설정)
ifconfig 에서 설정된 IP 주소는 시스템이 재 시작하게 되면 반영이 되지 못한다. 따라서 시스템의 네트워크를 설정에서 영구적으로 반영 되도록 해야 한다. 

- 설정하기 전에 알아두어 야 할 것
1. IP Address
2. Subnet Mask
3. Gateway IP Address
4. DNS Server IP Address

네트워크 설정은 /etc/sysconfig/network-scrips/ifcfg-인터페이스 파일에서 한다.


- ip바꾸기 실습


	ifconfig 
	/ IP 10.0.2.15, NETMASK 255.255.255.0
	
	nslookup  
	/ DNS 168.126.63.1
	
	netstat-r  
	/ GATEWAY 10.0.2.2

<hr>


	cd /etc/sysconfig/network-scripts/
	
	vi ifcfg-enp0s3
	
	세팅변경
	BOOTPROTO= "static"

	아래에 추가
	IPADDR=10.0.2.15
	NETMASK=255.255.255.0
	GATEWAY=10.0.2.2
	DNS1=168.126.63.1
	DNS2=168.126.63.2

<hr>
	
	systemctl restart network
