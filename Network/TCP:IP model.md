# TCP/IP model

- TCP/IP

  - 미국 방위고등연구계획국에 의해 개발된 ARPANET에서 시작
  - 인터넷의 표준 프로토콜

- TCP/IP 계층구조
  - Network access Layer -> OSI 7계층 중 1, 2 계층
    - 물리적 인터페이스 및 인접한 노드(라우터) 사이의 발생할 수 있는 문제를 해결하여 신뢰성 있는 데이터 전송 보장
  - Internet Layer -> OSI 7계층 중 3 계층
    - End-to-end 사이의 경로 설정(routing) 및 망 연결
    - IP 프로토콜 사용
  - Transport Layer -> OSI 7계층 중 4 계층
    - End-to-end 사이에 발생할 수 있는 문제를 해결하여 신뢰성 있는 데이터 전송 보장
    - TCP 또는 UDP 프로토콜 사용
  - Application -> OSI 7계층 중 5, 6, 7 계층
    - FTP, HTTP, DHCP

![image](https://user-images.githubusercontent.com/52199223/158367269-7f9b849c-6826-4565-8d5f-41b4fa7a4b83.png)
