#AI #딥러닝 #자연어처리 #필수

## 정의
장기 의존성 문제를 해결한 순환 신경망, LSTM
- RNN의 장기의존성 문제 해결을 위해 Hidden Layer를 Input Gate, Output Gate, Forget Gate라는 세 가지 게이트를 이용하여 해결한 알고리즘
- 중요한 정보는 오래 기억하고, 불필요한 정보는 잊는 메커니즘
## 키워드
* Forget Gate, Input Gate, Output Gate, Cell State, 장기 의존성
## 암기법
* LSTM 게이트: ==포인아== (Forget, Input, Output)
## 연관 토픽
- [[RNN]] - 기본 순환 신경망
- [[트랜스포머(Transformer)]] - 어텐션 기반 모델
- [[자연어 처리(NLP)]] - 언어 처리
## 게이트 구조
```
┌─────────────────────────────────────────────┐
│                  LSTM Cell                  │
│  ┌─────────┐  ┌─────────┐  ┌─────────┐      │
│  │ Forget  │  │  Input  │  │ Output  │      │ 
│  │  Gate   │  │  Gate   │  │  Gate   │      │
│  └────┬────┘  └────┬────┘  └────┬────┘      │
│       │            │            │           │
│       ▼            ▼            ▼           │
│  [Cell State] ─────────────────────→ [h_t]  │
└─────────────────────────────────────────────┘
```
## 3가지 게이트
| 게이트 | 역할 | 수식 |
|--------|------|------|
| ==Forget Gate== | 이전 정보 중 버릴 정보 결정 | f_t = σ(W_f·[h_{t-1}, x_t] + b_f) |
| ==Input Gate== | 새로운 정보 중 저장할 정보 결정 | i_t = σ(W_i·[h_{t-1}, x_t] + b_i) |
| ==Output Gate== | 출력할 정보 결정 | o_t = σ(W_o·[h_{t-1}, x_t] + b_o) |
## LSTM vs GRU
| 구분 | LSTM | GRU |
|------|------|-----|
| 게이트 수 | 3개 (Forget, Input, Output) | 2개 (Reset, Update) |
| 파라미터 | 많음 | 적음 |
| 데이터 양 | 많을 때 유리 | 적을 때 유리 |
| 상태 | Cell State + Hidden State | Hidden State만 |
| 성능 | 비슷 | 비슷 |
## 활용 분야
- 기계 번역 (Machine Translation)
- 음성 인식 (Speech Recognition)
- 텍스트 생성 (Text Generation)
- 시계열 예측 (Time Series Prediction)
