#정보관리기술사 #디지털서비스 #C-ITS #협력지능형교통 #정리

## 정의
**협력형 지능형교통체계, C-ITS**
- 양방향 오픈 플랫폼 기반으로 차량·인프라·보행자 간 실시간 정보를 교환하여 서비스를 제공하는 협력형 ITS(Cooperative-Intelligent Transport Systems)
- 5G-V2X 기반으로 차량과 모든 객체 간 양방향 통신을 통해 안전운전 및 자율주행을 지원하는 차세대 교통 체계
## 키워드
* V2X, V2V, V2I, V2P, V2C, IVN, 5G-V2X, Seamless, 상황능동형, WAVE, DSRC
## 암기법
* V2(CIVP) IVN (V2C, V2I, V2V, V2P, IVN) - 5대 통신 유형
## 특징
- Seamless: 끊김 없는 연속적 교통 정보 제공
- 서비스 융합: 안전·교통·편의 서비스의 통합 제공
- 상황능동형: 실시간 교통 상황에 능동적으로 대응
- 5G-V2X: 5G 기반 초저지연 차량 사물 통신
## 목적
- 차량·인프라·보행자 간 실시간 정보 교환으로 교통 안전 향상
- 자율주행 협력 지원을 통한 스마트 교통 체계 실현
## 구성요소
- V2C(Vehicle to Cloud): 차량과 클라우드 간 통신
- V2I(Vehicle to Infrastructure): 차량과 도로 인프라 간 통신
- V2V(Vehicle to Vehicle): 차량 간 직접 통신
- V2P(Vehicle to Pedestrian): 차량과 보행자 간 통신
- IVN(In-Vehicle Network): 차량 내부 네트워크 (CAN, LIN, FlexRay)
- 5G-V2X: 5G 기반 초저지연·고신뢰 차량 통신
- OBU(On Board Unit): 차량 탑재 통신 장치
- RSU(Road Side Unit): 도로변 통신 장치
## 기반 서비스
- 안전운전 서비스: 충돌 경고, 노면 상태 정보, 작업구간 경고
- 자율주행 서비스: 협력 자율주행, 군집주행(Platooning)
## 구성도
```
[C-ITS 통신 구성]

       Cloud(V2C)
          │
  ┌───────┼───────┐
  │       │       │
  RSU ──V2I── OBU(차량) ──V2V── OBU(차량)
(도로인프라)    │                    │
               V2P                  IVN
               │                 (차량내부)
            보행자

[기반서비스]
  안전운전                자율주행
  ├─ 충돌 경고           ├─ 협력 자율주행
  ├─ 노면 상태 정보      └─ 군집주행(Platooning)
  └─ 작업구간 경고
```
## 연관 토픽
- [[Smart Car(자율주행)]] - 자율주행 차량
- [[5G]] - V2X 통신 인프라
- [[IoT]] - 사물 통신
- [[디지털 트윈(Digital Twin)]] - 교통 시뮬레이션
