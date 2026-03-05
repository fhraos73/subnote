#AI #딥러닝 #자연어처리 #필수

## 정의
어텐션 메커니즘 기반의 시퀀스 처리 모델, 트랜스포머
- RNN(Recurrent Neural Network)을 탈피하고 seq2seq의 인코더-디코더 모델과 셀프 어텐션(Self-Attention) 구조만으로 구현한 자연어 처리 모델
- "Attention is All You Need" 논문(2017)에서 제안
## 키워드
* Self-Attention, Multi-Head Attention, Positional Encoding, 인코더, 디코더
## 암기법
* Transformer = Attention is All You Need
* 구성: ==셀멀포피== (셀프어텐션, 멀티헤드, 포지셔널인코딩, 피드포워드)
## 연관 토픽
- [[LLM]] - 대규모 언어 모델
- [[RNN]] - 순환 신경망
- [[LSTM]] - 장단기 메모리
## 핵심 구성요소
```
┌─────────────────────────────────────────┐
│              Transformer                │
│  ┌─────────────┐    ┌─────────────┐     │
│  │   인코더      │    │   디코더     │     │
│  │  Encoder    │ →  │  Decoder    │     │
│  │             │    │             │     │
│  │ Self-Attn   │    │ Masked Attn │     │
│  │ Feed Forward│    │ Cross Attn  │     │
│  │             │    │ Feed Forward│     │
│  └─────────────┘    └─────────────┘     │
└─────────────────────────────────────────┘
```
## 핵심 메커니즘
- ==셀프 어텐션(Self-Attention)==: 입력 시퀀스 내 모든 위치 간 관계 학습
- ==멀티헤드 어텐션(Multi-Head Attention)==: 여러 어텐션을 병렬로 수행
- ==포지셔널 인코딩(Positional Encoding)==: 위치 정보 추가 (순서 정보)
- ==피드포워드 네트워크(Feed Forward)==: 비선형 변환
## 어텐션 수식
```
Attention(Q, K, V) = softmax(QK^T / √d_k) × V
```
- Q(Query): 현재 단어의 표현
- K(Key): 다른 단어들의 표현
- V(Value): 실제 정보
## 장점 vs RNN
| 구분 | Transformer | RNN |
|------|-------------|-----|
| 병렬처리 | 가능 | 불가능 |
| 장기의존성 | 해결 | 문제 있음 |
| 학습속도 | 빠름 | 느림 |
| 메모리 | 많이 필요 | 적게 필요 |
## 파생 모델
- ==BERT==: 양방향 인코더 (이해 특화)
- ==GPT==: 단방향 디코더 (생성 특화)
- ==T5==: 인코더-디코더 통합
- ==ViT==: 비전 트랜스포머 (이미지)
## 활용 분야
- NLP: 기계 번역, 텍스트 생성, 질의응답
- 컴퓨터 비전: ViT, DETR
- 음성 인식: Whisper
- 단백질 구조 예측: AlphaFold
