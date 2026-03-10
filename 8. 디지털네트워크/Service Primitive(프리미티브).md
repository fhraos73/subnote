#디지털네트워크 #프리미티브 #OSI #옵션 #디지털네트워크/OSI/프로토콜
## 정의
계층 간 서비스 요청 인터페이스, Service Primitive
- OSI 참조 모델에서 인접 계층 간 서비스를 요청하고 응답하는 표준 인터페이스
- 상위 계층이 하위 계층의 서비스를 이용하기 위한 기본 연산 단위
## 키워드
* Request, Indication, Response, Confirm, SAP, 연결형, 비연결형
## 암기법
* 프리미티브 4종: 리인레콘(Request, Indication, Response, Confirm)
* 연결형 순서: 요지응확(요청→지시→응답→확인)
## 구성요소
| 구분 | 설명 | 방향 |
|------|------|------|
| Request | 서비스 요청 | 상위→하위 |
| Indication | 서비스 도착 알림 | 하위→상위 |
| Response | 서비스 응답 | 상위→하위 |
| Confirm | 서비스 완료 확인 | 하위→상위 |
| SAP | 서비스 접근점 | 계층 간 인터페이스 |
## 프리미티브 유형
| 유형 | 프리미티브 | 설명 |
|------|-----------|------|
| 연결형 | CONNECT | 연결 설정 |
| 연결형 | DATA | 데이터 전송 |
| 연결형 | DISCONNECT | 연결 해제 |
| 비연결형 | UNITDATA | 단일 데이터 전송 |
## 구성도
```
[Service Primitive 동작]

  송신측                              수신측
┌────────┐                         ┌────────┐
│ Layer  │                         │ Layer  │
│  N+1   │                         │  N+1   │
└───┬────┘                         └───▲────┘
    │ Request                          │ Indication
    ▼                                  │
┌───────────────────────────────────────────────┐
│                   Layer N                      │
└───────────────────────────────────────────────┘
    │                                  ▲
    │ Confirm                          │ Response
    ▼                                  │
┌───┴────┐                         ┌───┴────┐
│ Layer  │                         │ Layer  │
│  N+1   │                         │  N+1   │
└────────┘                         └────────┘

[연결형 서비스 흐름]
  Client                            Server
    │                                  │
    │──── CONNECT.request ────────────▶│
    │                                  │──▶ CONNECT.indication
    │◀─── CONNECT.confirm ─────────────│
    │                    CONNECT.response◀──│
    │                                  │
    │──── DATA.request ───────────────▶│
    │                                  │──▶ DATA.indication
    │                                  │
    │──── DISCONNECT.request ─────────▶│
    │                                  │──▶ DISCONNECT.indication

[SAP (Service Access Point)]
┌─────────────────────────────────┐
│         Upper Layer (N+1)       │
└──────────────┬──────────────────┘
               │ SAP (서비스 접근점)
┌──────────────▼──────────────────┐
│         Lower Layer (N)         │
└─────────────────────────────────┘
```
## 연관 토픽
- [[OSI 7 Layers]] - OSI 참조 모델
- [[네트워크 프로토콜]] - 통신 규약
- [[TCP]] - 연결형 전송 프로토콜
