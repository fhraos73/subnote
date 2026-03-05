#SW공학 #관점지향

## 정의
AOP(Aspect-Oriented Programming)
횡단 관심사를 분리하여 모듈성을 높이는 프로그래밍 패러다임, 관점지향 프로그래밍
- 비즈니스 로직(Core Concern)과 공통 기능(Cross-cutting Concern)을 분리하여 관리
- 로깅, 보안, 트랜잭션 등 여러 모듈에 흩어진 중복 코드를 별도의 '관점(Aspect)'으로 모듈화함
## 키워드
* 횡단 관심사, 분리(Separation), Aspect, Weaving, 프록시(Proxy)
## 암기법
* 횡단관심사 (여러 모듈을 가로지르는 공통 기능)
- 코조 위애포 어크
## 구성요소
- Core Concern: 필수요구사항
- Join Point: 핵심관심사 횡단위치 
-  Weaving: Joint Point에 Advice 삽입
- Aspect: Point Cut + Advice 캡슐화
- Point Cut: 언제 삽입?
- Advice:  횡단관심사 구현부
- Crosscutting Concern: 공통기능(보안, 인증)
## 구성도
![[Pasted image 20260122001832.png]]
## 연관 토픽
- [[객체지향 프로그래밍]] - 객체지향
- [[모듈화]] - 모듈화
