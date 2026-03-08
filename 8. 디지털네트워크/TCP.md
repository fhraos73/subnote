#디지털네트워크 #TCP #전송계층 #필수
## 정의
연결지향 신뢰성 전송 프로토콜, TCP
- Transmission Control Protocol, OSI 4계층에서 동작하는 연결지향형 프로토콜
- 3-Way Handshake로 연결 설정, 흐름/오류/혼잡 제어로 신뢰성 보장
## 키워드
* 3-Way Handshake, 4-Way Handshake, 시퀀스번호, ACK, 슬라이딩윈도우, 재전송
## 암기법
* 3-Way: 신신아(SYN→SYN+ACK→ACK)
* 4-Way: 핀아핀아(FIN→ACK→FIN→ACK)
* TCP 특징: 연신순흐오혼(연결지향, 신뢰성, 순서보장, 흐름제어, 오류제어, 혼잡제어)
## TCP 헤더 구조
| 필드 | 크기 | 설명 |
|------|------|------|
| Source Port | 16bit | 송신 포트 번호 |
| Destination Port | 16bit | 수신 포트 번호 |
| Sequence Number | 32bit | 세그먼트 순서 번호 |
| ACK Number | 32bit | 다음 수신 기대 번호 |
| Flags | 6bit | SYN, ACK, FIN, RST, PSH, URG |
| Window Size | 16bit | 수신 윈도우 크기 |
| Checksum | 16bit | 오류 검출 |
## 주요 기능
| 기능 | 설명 | 기법 |
|------|------|------|
| 연결 관리 | 연결 설정/해제 | 3-Way/4-Way Handshake |
| 신뢰성 보장 | 데이터 손실 방지 | ACK, 재전송 |
| 순서 보장 | 순서대로 전달 | Sequence Number |
| 흐름 제어 | 송수신 속도 조절 | 슬라이딩 윈도우 |
| 혼잡 제어 | 네트워크 혼잡 방지 | Slow Start, AIMD |
## 구성도
```
[3-Way Handshake - 연결 설정]
  Client                           Server
    │                                │
    │──── SYN (seq=x) ──────────────▶│  LISTEN
    │                                │
    │◀─── SYN+ACK (seq=y, ack=x+1) ──│
    │                                │
    │──── ACK (ack=y+1) ────────────▶│  ESTABLISHED
    │                                │

[4-Way Handshake - 연결 해제]
  Client                           Server
    │                                │
    │──── FIN (seq=u) ──────────────▶│  FIN_WAIT_1
    │                                │
    │◀─── ACK (ack=u+1) ─────────────│  CLOSE_WAIT
    │                                │  FIN_WAIT_2
    │◀─── FIN (seq=v) ───────────────│
    │                                │
    │──── ACK (ack=v+1) ────────────▶│  TIME_WAIT
    │                                │  CLOSED

[TCP 헤더 구조 (20~60 bytes)]
┌────────────────────┬────────────────────┐
│   Source Port (16) │   Dest Port (16)   │
├────────────────────┴────────────────────┤
│         Sequence Number (32)            │
├─────────────────────────────────────────┤
│       Acknowledgment Number (32)        │
├────┬────────┬──────┬────────────────────┤
│Hlen│Reserved│Flags │  Window Size (16)  │
├────┴────────┴──────┼────────────────────┤
│   Checksum (16)    │  Urgent Ptr (16)   │
├────────────────────┴────────────────────┤
│            Options (가변)               │
└─────────────────────────────────────────┘
```
## 연관 토픽
- [[TCP 혼잡제어]] - TCP 혼잡 제어 알고리즘
- [[UDP]] - 비연결형 전송 프로토콜
- [[Transport(4) - 전송 계층]] - 전송 계층
