# 제목 없음

복습: No
작성일시: 2021년 9월 29일 오전 9:32

1. **ping**
    
    ```
    ping www.douzone.com
    ```
    
    - cmd창에서 ping + url을 통해 ping 테스트를 할 수있으며 이 테스트를 통해 TTL(Time To Live)을 확인할 수 있다.
    - 각 Router들은 TTL이 장비를 거치면서 패킷이 거쳐갈때마다 TTL 값을 하나씩 내림, TTL이 0이 되면 소멸함. (OS 마다 TTL값은 다름)
    
2. **리눅스에서 traceroute 확인**
    
    ```
    yum -y install traceroute
    traceroute url
    ```
    
    - traceroute를 설치하고, traceroute + url을 통해 실행
    - ping -c 5 [www.google.com](http://www.google.com/) : 5번만 실행

3. **127.0.0.1 ping 막기**
    
    ```
    cat /proc/sys/net/ipv4/icmp_echo_ignore_all
    -> 확인
    
    vi /etc/sysctl.conf 
    -> 맨 밑줄에 net.ipv4.icmp_echo_ignore_all=1 추가
    
    sysctl -p
    ping 127.0.0.1
    ```
    
2.  **hostname**