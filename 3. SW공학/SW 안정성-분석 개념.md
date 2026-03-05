#SW공학 #안정성 #신뢰성 #필수

## 정의
소프트웨어 안전과 신뢰, SW 안정성
- 소프트웨어가 요구된 기능을 오류 없이 수행하고, 위험한 상황을 방지하는 능력
- 신뢰성(Reliability)은 결함 없는 동작, 안전성(Safety)은 위험 방지에 초점
## 키워드
- MTTF, MTBF, MTTR, Availability, Failure Rate
- Hazard, Risk, SIL, Fail-Safe, Fault Tolerance
- FTA, FMEA, HAZOP
- 신뢰성, 안전성, 가용성
## 암기법
- 신뢰성 3대 메트릭: 엠티 삼형제 (MTTF-MTBF-MTTR)
- 안전 대응: 페세톨 (Fail-Safe-Fail-Secure-Fault Tolerance)
- 분석 3기법: 에페하 (FTA-FMEA-HAZOP)
## 목적
- 시스템의 신뢰성 및 안전성 확보
- 고장 및 위험 요인 분석으로 사고 예방
## 구성요소
### 신뢰성(Reliability) 메트릭
- MTTF(Mean Time To Failure): 평균 고장 시간
- MTBF(Mean Time Between Failures): 평균 고장 간격
- MTTR(Mean Time To Repair): 평균 수리 시간
- Availability(가용성): MTBF / (MTBF + MTTR)
- Failure Rate(고장률): 단위 시간당 고장 발생 횟수
### 안전성(Safety) 개념
- Hazard(위험): 사고를 유발할 수 있는 상황
- Risk(리스크): 위험 발생 확률 × 심각도
- Safety-Critical System: 안전 필수 시스템
- Fail-Safe: 고장 시 안전한 상태로 전환
- Fail-Secure: 고장 시 보안 상태 유지
- Fault Tolerance(결함 허용): 오류에도 계속 동작
### 분석 기법
- FTA(Fault Tree Analysis): 결함 트리 분석
- FMEA(Failure Mode and Effects Analysis): 고장 모드 영향 분석
- HAZOP(Hazard and Operability Study): 위험 운용성 분석
## 구성도
```
[신뢰성 메트릭 관계]

    동작 ──MTTF──> 고장 ──MTTR──> 수리 ──> 동작
    │                                      │
    └──────────────MTBF──────────────────┘

Availability = MTBF / (MTBF + MTTR)

예시:
MTTF = 100시간
MTTR = 4시간
MTBF = 100시간
가용성 = 100 / (100+4) = 96.15%

[안전성 레벨]

SIL (Safety Integrity Level)
├─ SIL 4: 10⁻⁵ ~ 10⁻⁴ (최고)
├─ SIL 3: 10⁻⁴ ~ 10⁻³
├─ SIL 2: 10⁻³ ~ 10⁻²
└─ SIL 1: 10⁻² ~ 10⁻¹ (최저)

[리스크 매트릭스]

      심각도
      │ 높음 │ 중간 │ 낮음 │
확률──┼──────┼──────┼──────┤
높음 │ 높음 │ 높음 │ 중간 │
중간 │ 높음 │ 중간 │ 낮음 │
낮음 │ 중간 │ 낮음 │ 낮음 │

[결함 허용 기법]

1. Redundancy (중복)
   - N-Version Programming
   - Backup System

2. Diversity (다양성)
   - 다른 알고리즘 사용
   - 다른 개발팀

3. Recovery (회복)
   - Checkpoint/Restart
   - Rollback
```
## 연관 토픽
- [[FTA]] - 결함 트리 분석
- [[FMEA]] - 고장 모드 영향 분석
- [[HAZOP]] - 위험 운용성 분석
## 특징
- 정량화: 메트릭으로 측정 가능
- 예방성: 위험 사전 방지
- 지속성: 운영 기간 전체 적용
- 보증성: 안전 수준 보증
