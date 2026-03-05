#정보관리기술사 #디지털서비스 #SCADA #산업제어 #ICS #정리

## 정의
산업 감시 제어 데이터 수집 시스템, SCADA
- Supervisory Control And Data Acquisition, 원격지의 산업 설비를 중앙에서 감시·제어하고 데이터를 수집·분석하는 산업 제어 시스템
- 퍼듀(Purdue) 모델에서 Cell/Area 영역에 위치하며 DCS와 함께 산업 제어 핵심 시스템
## 키워드
* Supervisory Control, Data Acquisition, PLC, RTU, HMI, DCS
* Purdue 모델, ICS, OT 보안, MODBUS, DNP3, OPC-UA
## 암기법
* SCADA = S(감시) + C(제어) + A(그리고) + D(데이터) + A(수집)
* 구성: 에피알마 (HMI-PLC-RTU-Master Station)
## 특징
- ==원격 모니터링==: 지리적으로 분산된 설비를 중앙에서 실시간 감시
- ==별도 소프트웨어==: 전용 SCADA 소프트웨어 및 데이터베이스 연동 필요
- ==PLC 연동==: PLC(Programmable Logic Controller)와 연계한 자동 제어
- ==경보 관리==: 이상 상태 감지 시 자동 경보 및 알림
## 목적
- 산업 설비의 효율적 운영 및 가동률 극대화
- 실시간 이상 감지·대응으로 안전성 확보
## 구성요소
- ==HMI(Human Machine Interface)==: Machine의 상태를 인간이 이해하기 쉬운 인터페이스, SCADA 시스템 소프트웨어 및 데이터베이스 연동
- ==PLC(Programmable Logic Controller)==: 현장 설비 자동 제어 장치
- ==RTU(Remote Terminal Unit)==: 원격 현장 데이터 수집·전송 장치
- ==Master Station==: 중앙 감시·제어 서버
- ==통신 네트워크==: PLC/RTU와 Master 간 통신 (MODBUS, DNP3, OPC-UA)
- ==히스토리안(Historian)==: 시계열 데이터 저장·분석 DB
## 구성도
```
[퍼듀(Purdue) 모델에서 SCADA 위치]

Level 4-5 │ Enterprise    │ ERP / 인터넷
──────────┤               │
Level 3   │ Operations    │ MES / 생산관리
──────────┤               │
Level 2   │ Control       │ ★ SCADA / DCS / HMI ★
──────────┤               │
Level 1   │ Basic Control │ PLC / RTU / 센서
──────────┤               │
Level 0   │ Process       │ 물리적 설비·장비

[SCADA 시스템 구성도]

       ┌──────────── Master Station ────────────┐
       │  ┌───────┐  ┌──────────┐  ┌─────────┐ │
       │  │ SCADA │  │Historian │  │  경보    │ │
       │  │  S/W  │  │   DB     │  │  관리   │ │
       │  └───┬───┘  └──────────┘  └─────────┘ │
       └──────┼─────────────────────────────────┘
              │  통신 네트워크 (MODBUS/DNP3)
       ┌──────┴──────┬──────────────┐
       ▼             ▼              ▼
  ┌─────────┐  ┌─────────┐   ┌─────────┐
  │  HMI    │  │  PLC    │   │  RTU    │
  │ (화면)  │  │ (제어)   │   │ (원격)  │
  └─────────┘  └────┬────┘   └────┬────┘
                    ▼              ▼
              [현장 설비]    [원격 설비]
              센서/액추에이터  센서/액추에이터
```
## 연관 토픽
- [[CPS(Cyber-Physical System)]] - 물리-사이버 시스템 연동
- [[스마트 팩토리(Smart Factory)]] - SCADA 활용 지능형 공장
- [[인더스트리 4.0, 5.0]] - 산업 제어 시스템 진화
- [[MES]] - 제조실행시스템 연동
## SCADA vs DCS 비교
| 구분 | SCADA | DCS |
|------|-------|-----|
| 적용 범위 | 광역 분산 설비 | 단일 공장/플랜트 |
| 통신 | 원격 통신(WAN) | 로컬 통신(LAN) |
| 응답 시간 | 상대적 느림 | 실시간 제어 |
| 주요 분야 | 전력, 수도, 가스 | 석유화학, 발전 |
| 제어 방식 | 감시 중심 | 제어 중심 |
