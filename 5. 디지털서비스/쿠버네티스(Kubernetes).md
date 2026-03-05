#정보관리기술사 #디지털서비스 #쿠버네티스 #컨테이너오케스트레이션 #클라우드네이티브 #정리
- [x] 
## 정의
컨테이너 오케스트레이션 플랫폼, 쿠버네티스
- 컨테이너화된 워크로드와 서비스를 관리하기 위한 이식성 있고 확장 가능한 오픈소스 컨테이너 오케스트레이션 플랫폼
- Google이 개발, CNCF(Cloud Native Computing Foundation)에서 관리하는 사실상 표준(De facto)
## 키워드
* k8s, Master Node, Worker Node, Pod, API Server, Scheduler, Controller Manager
* kube-proxy, kubelet, etcd, Service, Deployment, Ingress, ConfigMap
## 암기법
* Master 구성: 마노포컨 (API Server-Scheduler-Controller Manager-etcd)
* k8s = Kubernetes (k + 8글자 + s)
## 특징
- ==자동 스케일링==: HPA/VPA를 통한 부하 기반 자동 확장·축소
- ==자가 치유==: 장애 Pod 자동 감지·재시작·교체
- ==서비스 디스커버리==: DNS 기반 서비스 자동 검색 및 로드밸런싱
- ==롤링 업데이트==: 무중단 배포 및 자동 롤백 지원
## 목적
- 대규모 컨테이너 운영의 자동화 및 효율화
- 애플리케이션의 고가용성·확장성·이식성 확보
## 구성요소
- ==Master Node==
  - ==API Server==: 외부 Request 수신, 클러스터 관리의 진입점(RESTful API)
  - ==Scheduler==: 요청에 대한 적합한 Node 선출, Pod 배치 결정
  - ==Controller Manager==: 노드 상태 파악하고 관리, 원하는 상태(Desired State) 유지
  - ==etcd==: 클러스터 구성 정보 저장 (분산 Key-Value 저장소)
- ==Worker Node (Agent)==
  - ==kubelet==: Pod 생명주기 관리, Master와 통신
  - ==kube-proxy==: Pod 간 Route, Load Balancing, 네트워크 규칙 관리
  - ==Container Runtime==: 컨테이너 실행 (containerd, CRI-O)
- ==Pod==: 쿠버네티스 최소 배포 단위, 1개 이상의 컨테이너 그룹
- ==Service==: Pod 그룹에 대한 네트워크 접근 추상화
- ==Ingress==: 외부 트래픽을 클러스터 내부 서비스로 라우팅
## 구성도
```
┌──────────────────── Kubernetes Cluster ────────────────────┐
│                                                            │
│  ┌───────────── Master Node ──────────────┐                │
│  │  ┌───────────┐  ┌──────────┐           │                │
│  │  │ API Server│  │Scheduler │           │                │
│  │  └─────┬─────┘  └──────────┘           │                │
│  │  ┌─────┴─────┐  ┌──────────┐           │                │
│  │  │Controller │  │  etcd    │           │                │
│  │  │ Manager   │  │ (저장소)  │           │                │
│  │  └───────────┘  └──────────┘           │                │
│  └────────────────────────────────────────┘                │
│         │                                                  │
│  ┌──────┴──── Worker Node 1 ──┐  ┌──── Worker Node 2 ──┐  │
│  │  ┌────────┐  ┌────────┐    │  │  ┌────────┐         │  │
│  │  │ Pod A  │  │ Pod B  │    │  │  │ Pod C  │         │  │
│  │  └────────┘  └────────┘    │  │  └────────┘         │  │
│  │  kubelet  kube-proxy       │  │  kubelet  kube-proxy │  │
│  └────────────────────────────┘  └──────────────────────┘  │
└────────────────────────────────────────────────────────────┘
```
## 연관 토픽
- [[컨테이너(Container)]] - 컨테이너 가상화 기술
- [[HPA(Horizontal Pod Autoscaler)]] - Pod 자동 스케일링
- [[DevOps]] - 클라우드 네이티브 운영
- [[MSA와 Monolithic Architecture]] - MSA 컨테이너 배포
- [[MSA 서비스 서비스 메쉬(Service Mesh)]] - 서비스 간 통신 관리
## 주요 오브젝트
| 오브젝트 | 설명 |
|---------|------|
| Pod | 최소 배포 단위 (1+ 컨테이너) |
| Deployment | Pod 복제본 관리, 롤링 업데이트 |
| Service | Pod 네트워크 접근 추상화 |
| Ingress | 외부 트래픽 라우팅 |
| ConfigMap | 설정 데이터 분리 관리 |
| Secret | 민감 정보 암호화 관리 |
| Namespace | 클러스터 내 가상 분리 |
