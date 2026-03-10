#디지털네트워크 #TCP #혼잡제어 #필수 #디지털네트워크/TCP/UDP
## 정의
네트워크 혼잡 방지 전송 제어, TCP Congestion Control
- 네트워크 혼잡 상황에서 송신측의 전송률을 조절하여 패킷 손실을 방지하는 메커니즘
- cwnd(혼잡윈도우)를 동적으로 조절하여 네트워크 안정성 확보
## 키워드
* cwnd, ssthresh, Slow Start, Congestion Avoidance, Fast Retransmit, Fast Recovery, AIMD
## 암기법
* 혼잡제어 4단계: 슬혼빠빠(Slow Start, 혼잡회피, 빠른재전송, 빠른회복)
* AIMD: 에이아이엠디(Additive Increase, Multiplicative Decrease)
## 주요 알고리즘
| 알고리즘 | 설명 | 동작 |
|----------|------|------|
| Slow Start | 초기 cwnd 지수 증가 | cwnd = cwnd × 2 |
| Congestion Avoidance | 혼잡 회피 선형 증가 | cwnd = cwnd + 1 |
| Fast Retransmit | 3 Dup ACK 시 즉시 재전송 | 타임아웃 대기 없이 재전송 |
| Fast Recovery | 빠른 회복 | ssthresh = cwnd/2, cwnd = ssthresh |
## TCP 혼잡제어 버전
| 버전          | 특징        | 알고리즘                            |
| ----------- | --------- | ------------------------------- |
| TCP Tahoe   | 초기 버전     | Slow Start, CA, Fast Retransmit |
| TCP Reno    | 빠른 회복 추가  | + Fast Recovery                 |
| TCP NewReno | 부분 ACK 처리 | Reno 개선                         |
| TCP CUBIC   | 리눅스 기본    | 3차 함수 기반 증가                     |
| TCP BBR     | 구글 개발     | 대역폭 기반 제어                       |
## 구성도
```
[혼잡제어 동작 흐름]

cwnd
  │
  │                    ┌─ 혼잡 발생 (패킷 손실)
  │                    │
  │              ●─────┤ ssthresh = cwnd/2
  │            ╱       │ cwnd = 1 (Tahoe)
  │          ╱         │ cwnd = ssthresh (Reno)
  │        ╱ Congestion│
  │      ╱   Avoidance │
  │    ╱ (선형 증가)    ▼
  │  ╱─────────────────●
  │╱  ssthresh         │
  ●───────────────────▶│
  │ Slow Start         │
  │ (지수 증가)         │
  └────────────────────┴──────▶ Time

[Slow Start & Congestion Avoidance]
┌─────────────────────────────────────────────────┐
│ RTT │ cwnd │ 상태                               │
├─────┼──────┼────────────────────────────────────┤
│  1  │   1  │ Slow Start (지수 증가)             │
│  2  │   2  │                                    │
│  3  │   4  │                                    │
│  4  │   8  │ ssthresh=8 도달                    │
│  5  │   9  │ Congestion Avoidance (선형 증가)   │
│  6  │  10  │                                    │
│  7  │  11  │ 혼잡 발생 → ssthresh=5, cwnd=1    │
└─────┴──────┴────────────────────────────────────┘

[Fast Retransmit & Fast Recovery]
  Sender                          Receiver
    │──── Segment 1 ─────────────▶│
    │◀─── ACK 2 ──────────────────│
    │──── Segment 2 ──────X (손실)│
    │──── Segment 3 ─────────────▶│
    │◀─── ACK 2 (Dup 1) ──────────│
    │──── Segment 4 ─────────────▶│
    │◀─── ACK 2 (Dup 2) ──────────│
    │──── Segment 5 ─────────────▶│
    │◀─── ACK 2 (Dup 3) ──────────│ ← 3 Dup ACK
    │                              │
    │──── Segment 2 (재전송) ─────▶│ Fast Retransmit
    │◀─── ACK 6 ──────────────────│
```
## 연관 토픽
- [[TCP]] - 전송 제어 프로토콜
- [[혼잡제어]] - 네트워크 혼잡 제어
- [[QoS]] - 서비스 품질
