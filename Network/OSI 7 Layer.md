# OSI 7 Layer

국제 표준화 기구 ISO가 확립한 개방화된 데이터 통신 환경에 적합한 계층적 구현 모델의 표준???

> 네트워크에 연결된 구조가 서로 다른 컴퓨터 사이에서 서로 통신이 가능하도록 한 표준 규격

- 계층구조
  - 통신 시스템의 기능을 7개의 각 계층에 나누어 배치
  - 각 계층은 다른 계층과 독립적 구현 가능
  - 각 계층은 서로 간 정의된 인터페이스를 통해 협조
  - 각 계층은 두 호스트간의 통신을 위해 고유의 프로토콜을 사용함
  - 테스트 및 변경이 용이함

### 1계층, Physical Layer (물리 계층)

- 사용자 장비를 네트워크에 접속할 수 있도록 함
- 물리적, 전기적 interface

### 2계층, Data link Layer (데이터 링크 계층)

- 서로 인접한 노드 사이에 발생할 수 있는 문제 해결, 신뢰성 있는 데이터 전송 보장
- 동기화
- 에러 검출 및 재전송
- 흐름 제어
- 두 가지 동작 방식
  - 연결성 : 데이터 전송 전에 연결 설정
  - 비연결성 : 사전에 연결 설정 없이 데이터 전송

### 3계층, Network Layer (네트워크 계층)

- End-to-end 사이의 경로 설정, 라우팅

### 4계층, Transport Layer (전송 계층)

- End-to-end 사이에 발생할 수 있는 문제 해결, 신뢰성 있는 데이터 전송 보장
- 순서화
- 에러 검출 및 복구
- 흐름 제어
- 혼잡 제어

### 5계층, Session Layer (세션 계층)

- 두 응용 사이의 세션(논리적 연결)이 잘 진행되도록 함
- 응용 환경에서 사용자 간의 대화 개념의 연결로 사용되므로 전송 계층의 연결과 구분됨

### 6계층, Presentation Layer (표현 계층)

- 두 기계 사이의 데이터 표현 방식의 차이를 해결 ex) ASCII vs EBCIDIC, 1의 보수 vs 2의 보수
- 데이터 압축과 복원
- 데이터 암호화와 복호화

### 7계층, Application Layer (응용 계층)

- 각 응용에 고유하게 필요한 기능을 수행
- web, email, ftp

## PDU

protocol data unit, OSI 7 계층 모델의 각 계층에서 사용되는 데이터 단위

- 1계층, 물리 계층 PDU 명칭 : bit
- 2계층, 데이터 링크 계층 PDU 명칭 : Frame
- 3계층, 네트워크 계층 PDU 명칭 : Packet
- 4계층, 전송 계층 PDU 명칭 : TCP에서는 segment, UDP에서는 datagram

## Encapsulation

송신 데이터에 각 계층에서 전달받은 데이터에 해당 계층의 프로토콜 정보인 특정 제어 정보를 헤더에 부착하여 하위 계층으로 전달함

## Decapsulation

Encapsulation된 데이터를 하위 계층에서 상위 계층으로 보내면서 헤더 정보를 각 계층에서 제거하고 해석하는 것

![image](https://user-images.githubusercontent.com/52199223/158362549-438671d8-31e8-4279-b8db-90c1f25eaa76.png)
