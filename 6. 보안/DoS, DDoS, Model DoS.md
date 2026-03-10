#정보관리기술사 #보안 #DoS #DDoS #정리 #보안/공격/위협

## 정의
서비스 가용성 침해 공격, DoS/DDoS
- DoS(Denial of Service): 정상적인 서비스 자원을 무리하게 요청해서 원활한 서비스가 제공될 수 없도록 하는 공격
- DDoS(Distributed DoS): 다수의 시스템에 분산 설치된 Agent를 통해 동시에 서비스 거부 공격을 수행하는 기법
- Model DoS : AI, LLM 특수 보안 위협
	- AI 모델 과도한 요청, 긴문맥 공격, 복잡한 쿼리 공격, API 부하 폭주, 악의적 입력

## 키워드
* SYN Flooding, Smurf, Slowloris, 좀비PC, C&C, 봇넷, 대역폭 소진, 사이버대피소

## 암기법
* 대어: (공격유형) 대역폭 소진 공격, 어플리케이션 마비 공격
* TCP UDP ICMP IP HTTP: (대역폭 소진) TCP/UDP/ICMP/IP Flooding
* 공탐수유: (APT 연계) 공격침입, 탐색, 수집, 유출

## 특징
- 가용성 침해: 정상 사용자의 서비스 접근 방해
- 분산 공격: 다수의 좀비PC 활용 (DDoS)
- 다양한 기법: 네트워크/애플리케이션 계층 공격
- 탐지 어려움: 정상 트래픽과 구분 어려움

## 목적
- 서비스 가용성 저하 및 마비
- 금전적 협박 (랜섬 DDoS)
- 경쟁사 방해 또는 정치적 목적

## 구성요소
| 구분 | 공격유형 | 설명 |
|------|----------|------|
| 대역폭 소진 | TCP Flooding | SYN, ACK, FIN Flooding |
| 대역폭 소진 | UDP Flooding | UDP 패킷 대량 전송 |
| 대역폭 소진 | ICMP Flooding | Smurf, Ping of Death |
| 대역폭 소진 | IP Flooding | IP 패킷 대량 전송 |
| 애플리케이션 | HTTP Flooding | GET/POST 요청 대량 전송 |
| 애플리케이션 | Slowloris | HTTP 헤더 불완전 전송 |
| 애플리케이션 | RUDY | POST 데이터 느린 전송 |
| 애플리케이션 | HashDoS | 해시 충돌 유발 |
| DDoS 인프라 | C&C 서버 | 좀비PC 명령 제어 서버 |
| DDoS 인프라 | 봇넷 | 감염된 좀비PC 네트워크 |

## 구성도
```
[DDoS 공격 구조]

[공격자] ──▶ [C&C 서버]
                 │
        ┌────────┼────────┐
        ▼        ▼        ▼
    [좀비PC]  [좀비PC]  [좀비PC]
        │        │        │
        └────────┼────────┘
                 ▼
           [공격 대상]
           (웹서버/네트워크)

[공격 유형]
    ┌────────────┬────────────┐
    ▼            ▼            ▼
[대역폭 소진]  [연결 고갈]  [애플리케이션]
(Flooding)    (SYN Flood)  (Slowloris)
```

## 연관 토픽
- [[TCP SYN Flooding]] - TCP 3-Way Handshake 악용
- [[Smurf]] - ICMP Echo 브로드캐스트 공격
- [[Slowloris]] - HTTP 연결 고갈 공격
- [[APT]] - 지능형 지속 위협
- [[랜섬웨어]] - 랜섬 DDoS 연계
