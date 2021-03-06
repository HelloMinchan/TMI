# Twelve-Factor App

소프트웨어를 만들 때 잘 만들기 위한 방법론.  
아키텍처를 설계할 때, 항상 유념하며 만들자!

링크 : [여기](https://12factor.net/)

## 1. Codebase (코드베이스)

하나의 앱에 하나의 레포를 유지하자는 원칙

### 나?

하나의 레포에서 환경변수로 서비스별 이미지를 분리해 여러 앱을 띄우고 있기에,  
여러 앱이 같은 코드를 공유하고 있다고 봐야할 것 같다.  
잘 지키지 못하고 있는 것 같다.

## 2. Dependencies (종속성)

패키지 매니저를 이용하고, 종속성 관리를 철저히 하자는 원칙

### 나?

Python 프로젝트의 경우 pip, Node.js프로젝트의 경우 npm 혹은 Yarn을 사용하고 있다.  
잘 지키고 있는 것 같다.

## 3. Config (설정)

환경변수 관리를 잘하자는 원칙이다 (보안적으로)

### 나?

AWS의 Parameter Store를 사용하여 관리하고 있다.  
레포에 환경변수가 올라가지 않도록 하고 있으므로,  
잘 지키고 있는 것 같다.

## 4. Backing services (백엔드 서비스)

백엔드 서비스에 물려있는 각종 리소스들을 느슨하게 결합하자는 원칙  
(애플리케이션에 연결된 리소스가 바뀌어도 애플리케이션단의 코드가 변경되지 않게 한다.)

### 나?

사실, 이 원칙을 잘 이해한건지도 모르겠다.  
예를 들어, 기존 MySQL에 물려놓은 걸 코드단의 변경 없이 AWS RDS로 바꿀 수 있겠냐? 라는 것 같은데,  
사실 엔진이 같으면 가능하고 MySQL에서 Oracle로 간다든지? 하면 당연히 비즈니스 로직이 바뀌는게 아닌가? (ORM을 쓰더라도)  
프론트 같은 경우에 지도 API를 Google에서 Naver로 바꾼다 하더라도 제공하는 API가 달라질 거 같은데...  
아마 잘 지키지 못하고 있는 것 같다.

## 5. Build, release, run (빌드, 릴리즈, 실행)

빌드 -> 릴리즈 -> 실행 단계를 엄격하게 구분하자는 원칙

### 나?

릴리즈 기능을 잘 사용하고 있지 않다..
잘 지키지 못하고 있는 것 같다.

## 6. Processes (프로세스)

애플리케이션을 stateless 프로세스로 실행하자는 원칙이다.

### 나?

백엔드에선 기본적으로 RDB나 NoSQL을 사용하고 캐시를 위해 Redis를 사용하고 있다.  
프론트에선 쿠키, 로컬 스토리지를 사용하고 있다. (React의 Redux나 useState는 그럼 위배되는 건가?)  
잘 지키고 있는 것 같다.

## 7. Port binding (포트 바인딩)

포트 바인딩을 사용하자는 원칙

### 나?

잘 지키고 있는 것 같다.

## 8. Concurrency (동시성)

Scale Up 보다 Scale Out을 지향하고 worker 프로세스를 사용하자는 원칙

### 나?

프로젝트를 Scale Out이 가능하게 설계하고, 크론이나 무거운 작업은 worker에 던지고 있다.  
잘 지키고 있는 것 같다.

## 9. Disposability (폐기 가능)

프로세스를 신속하게 시작 및 종료 가능하게 만들자는 원칙

### 나?

Docker를 사용하며, 주로 ECS Fargate위에서 배포 하므로 Auto Scaling과 무중단 배포가 가능하다.  
잘 지키고 있는 것 같다.

## 10. Dev/prod parity (개발/프로덕션환경 일치)

dev, stag, prod 환경을 비슷하게 유지하자는 원칙

### 나?

시간의 차이, 담당자의 차이, 툴의 차이 모두  
잘 지키고 있는 것 같다.

## 11. Logs (로그)

로그를 디스크에 저장하지 않고 앱 외부에 이벤트 스트림으로 취급하자는 원칙

### 나?

기본적으로 프로덕트가 AWS 위에 올려져 있기에 CloudWatch를 통해 로그를 수집 및 가공하며,  
에러 로그의 경우 슬랙으로 발송되도록 처리해놨다.
앞으로 데이터 파이프라인이 잘 구축되면 스트림 로깅이 가능해질 것 같다.
기본은 잘 지키고 있는 것 같다.

## 12. Admin processes (어드민 프로세스)

일회성 관리 혹은 유지보수를 위해 어드민 프로세스를 가능하게 만들자는 원칙

### 나?

Django 프로젝트의 경우 Shell 접속이 가능하므로 이미 유용하게 쓰고 있다.  
다만, Node.js 프로젝트의 경우 어떻게 해야 할지 찾아봐야 할 것 같다.  
Django 프로젝트를 제외하면 잘 지키지 못하고 있는 것 같다.
