# NAT gateways vs NAT instances

NAT instances는 고정 ip를 가진 인스턴스를 띄워 NAT를 구축하는 방식이고 NAT gateways는 AWS의 NAT 매니징 서비스이다.

public 서브넷에 둔 뒤, 고정 ip를 연동한다.

보통, private 서브넷에 속한 서비스들을 외부에 노출시켜야 할 때 사용한다.  
ex) 써드파티 서비스 인증 연동

두 방식의 차이점은
[여기](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-comparison.html) 참조

내가 느끼기에 가장 큰 차이점은, 포트포워딩이 되냐 안되냐이다.  
또한, AWS에서는 NAT gateways를 더 권장하는 것 같다.  
NAT instances에 사용하는 ami를 크리티컬한 보안 업데이트 빼고는 더 이상 지원 하지 않는다.  
(이미지 os 자체가 18버전이다.)
