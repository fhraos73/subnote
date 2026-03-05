#정보관리기술사 #디지털서비스 #쿠버네티스 #오토스케일링 #옵션 #정리

## 정의
Pod 수평 자동 확장기, HPA
- 부하에 따라 Pod의 개수를 자동으로 늘리거나 줄이는 쿠버네티스 오토 스케일링 기능
- CPU·메모리 사용률 또는 사용자 정의 메트릭 기반으로 Deployment의 Replica 수를 동적 조정
## 키워드
* HPA, VPA, Pod, Replica, 스케일링, Metrics Server, CPU 사용률
* minReplicas, maxReplicas, targetCPUUtilizationPercentage, Custom Metrics
## 암기법
* HPA vs VPA: "수평(H)은 개수, 수직(V)은 크기"
* H=Horizontal=수평=Pod 개수 조정, V=Vertical=수직=Pod 자원 조정
## 특징
- ==자동 확장==: CPU·메모리 임계치 초과 시 Pod 수 자동 증가
- ==자동 축소==: 부하 감소 시 불필요한 Pod 자동 제거
- ==메트릭 기반==: Metrics Server로부터 실시간 자원 사용량 수집
- ==선언적 관리==: YAML 매니페스트로 스케일링 정책 정의
## 목적
- 트래픽 변동에 따른 서비스 가용성 자동 확보
- 불필요한 자원 낭비 방지 및 비용 최적화
## 구성요소
- ==Metrics Server==: Pod의 CPU·메모리 사용량 수집
- ==HPA Controller==: 메트릭 수집 → 목표값 비교 → Replica 수 결정
- ==Deployment==: HPA가 관리하는 Pod 집합
- ==Custom Metrics API==: 사용자 정의 메트릭 기반 스케일링 (Prometheus 연동)
## 구성도
```
┌─────────────────────────────────────────┐
│           HPA Controller                │
│  ┌──────────────────────────────────┐   │
│  │ 1. 메트릭 수집 (Metrics Server)   │   │
│  │ 2. 목표값 비교                    │   │
│  │ 3. Replica 수 계산               │   │
│  │ 4. Deployment 업데이트            │   │
│  └──────────────────────────────────┘   │
└─────────────┬───────────────────────────┘
              │ Scale Up/Down
              ▼
┌──── Deployment (replicas: 2→5) ─────┐
│  ┌─────┐ ┌─────┐ ┌─────┐           │
│  │Pod 1│ │Pod 2│ │Pod 3│ +Pod4 +Pod5│
│  └─────┘ └─────┘ └─────┘           │
└─────────────────────────────────────┘

[HPA vs VPA 비교]
HPA: Pod 수 조정 (수평 확장)
  Pod Pod Pod → Pod Pod Pod Pod Pod

VPA: Pod 자원 조정 (수직 확장)
  [CPU:0.5 Mem:256M] → [CPU:2.0 Mem:1G]
```
## 연관 토픽
- [[쿠버네티스(Kubernetes)]] - 컨테이너 오케스트레이션 플랫폼
- [[컨테이너(Container)]] - 컨테이너 가상화
- [[MSA와 Monolithic Architecture]] - MSA 환경 스케일링
## HPA vs VPA 비교
| 구분 | HPA | VPA |
|------|-----|-----|
| 확장 방향 | 수평 (Pod 개수) | 수직 (Pod 자원) |
| 조정 대상 | Replica 수 | CPU·메모리 할당 |
| 적용 시점 | 실시간 | Pod 재시작 필요 |
| 적합 환경 | Stateless 서비스 | Stateful 서비스 |
| 병용 | VPA와 병용 시 주의 | HPA와 병용 시 주의 |
