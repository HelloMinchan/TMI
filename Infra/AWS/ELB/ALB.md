# ALB (Application Load Balancer)

OSI 7계층에서 7계층인 Application Layer에서 동작하는 로드밸런서이다.  
NGINX나 HAProxy처럼 HTTP/HTTPS 프로토콜의 부하분산을 지원하며,  
나는 주로 대부분의 백엔드 서비스에서 ALB를 사용하고있다.

7계층 위에서 도는 서비스라 NLB, CLB에 비해 다양한 기능을 제공하는데, 직접 사용하고 있는 쓸만한 기능으로는

- Path기반 라우팅
- Host기반 라우팅
- 리다이렉트
- 타겟으로 람다 설정 가능
- 웹소켓 지원 (NLB도 지원함)

등 이 있다.
