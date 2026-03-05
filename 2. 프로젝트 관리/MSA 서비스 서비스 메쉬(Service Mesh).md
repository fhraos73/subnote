#프로젝트관리 #아키텍처

## 정의
서비스 간 통신과 네트워크 관리를 담당하는 인프라 계층, 서비스 메쉬
- MSA 환경에서 각 서비스의 데이터를 관리/제어하여 Overload를 줄이기 위한 시스템
## 키워드
* 사이드카, 데이터/컨트롤 플레인, 서킷 브레이커
## 암기법
* 데이터 플레인 : SCDB (Sidecar, Circuit Breaker, Service Discovery, Busness Logic)
* 컨트롤 플레인
## 구성요소
- 데이터 플레인(Data Plane): 실제 서비스 간의 모든 네트워크 트래픽을 처리하는 프록시 계층
	- 사이드카(Sidecar): 개별 서비스 옆에 배치되어 통신을 대행하는 프록시 (예: Envoy)
	- Circuit Breaker : 연결 감지, 장애 대응
	- 서비스 검색(Discovery) : 트래픽 규칙 배포
	- Business Logic : 비즈니스 기능 데이터
- 컨트롤 플레인(Control Plane): 데이터 플레인의 동작을 제어하고 정책을 관리하는 계층 (예: Istio)
## 구성도 요소
* 아키텍처: 서비스 내부에 통신 로직을 넣지 않고 별도의 사이드카 프록시를 통해 통신
* 관계: API Gateway(외부 통신)와 Service Mesh(내부 통신)의 역할 분담
```
[Service A] -- (Local) --> [Sidecar A]
                               |
                        [Network/Policy] (Control Plane)
                               |
[Service B] -- (Local) --> [Sidecar B]
```
## 연관 토픽
- [[MSA와 Monolithic Architecture]] - MSA 아키텍처
- [[아키텍처 모델-패턴]] - 아키텍처 패턴
