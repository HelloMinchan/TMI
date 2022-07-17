# Region, Availability Zone

AWS에는 크게 Region이라는 국가별 사용 가능 지역이 존재한다.

> 서울(한국) Region은 `ap-northeast-2`이다.

그 Region안에서도 Availability Zone이 존재하는데,  
만약 Region에 Availability Zone이 1개일 경우 화재 등의 문제가 발생하면 서비스가 전부 죽어버린다.  
따라서, 한 Region에는 최소 2개 이상의 Availability Zone이 있으며,  
High Availability, 즉 고가용성을 확보하기 위해 서비스를 각기다른 Availability Zone에 서비스를 분산 배치한 후 LB로 묶는다.  
이또한 문제가 있는데 IDC간의 거리가 멀면 통신이 느릴 수 있다.  
그래서 같은 Region의 Availability Zone끼리는 전용선으로 연결하여 마치 한 건물인 것과 같은 속도가 보장된다고 한다.

이 글을쓴 22.07.18 현재 서울 Region에는 무려 4개의 Availability Zone이 있다.

Availability Zone의 명칭은 아래와 같이 Region에 알파벳 순으로 붙여진다.

- ap-northeast-2a
- ap-northeast-2b
- ap-northeast-2c
- ap-northeast-2d
