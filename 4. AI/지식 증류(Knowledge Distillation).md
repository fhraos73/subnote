#AI #모델경량화 #딥러닝

## 정의
대형 모델의 지식을 소형 모델로 전이하는 기법, 지식 증류
- 크고 복잡한 교사 모델(Teacher Model)의 지식을 작고 효율적인 학생 모델(Student Model)로 전달하는 모델 압축 기법
- 모델 경량화와 성능 유지를 동시에 달성
## 키워드
* Teacher, Student, Soft Labels, Temperature, KL Divergence
* Softmax
## 암기법
* 지식 증류 = 선생님(Teacher) → 학생(Student) 지식 전달
* 증류(Distillation) = 핵심만 추출
## 연관 토픽
- [[sLLM]] - 경량화 언어모델
- [[온디바이스 AI(Artificial Intelligence)]] - 엣지 AI
- [[연합학습(Federated Learning)]] - 분산 학습
## 구조
```
┌─────────────────────────────────────────────────┐
│                                                 │
│  ┌──────────────┐         ┌──────────────┐      │
│  │  교사 모델     │         │  학생 모델     │      │
│  │  (Teacher)   │         │  (Student)   │      │
│  │  대형/복잡     │         │  소형/간단     │      │
│  └──────┬───────┘         └──────┬───────┘      │
│         │                        │              │
│         ▼                        ▼              │
│    [Soft Labels]           [Predictions]        │
│    (확률 분포)              (예측 결과)             │
│         │                        │              │
│         └────────┬───────────────┘              │
│                  ▼                              │
│           [Distillation Loss]                   │
│           (KL Divergence)                       │
└─────────────────────────────────────────────────┘
```
## 핵심 개념
- ==교사 모델(Teacher)==: 사전 학습된 대형 모델
- ==학생 모델(Student)==: 학습할 소형 모델
- ==소프트 레이블(Soft Labels)==: 교사의 확률 분포 출력
- ==온도(Temperature)==: 확률 분포 평활화 파라미터
- ==증류 손실(Distillation Loss)==: KL Divergence 기반
## 손실 함수
```
L = α × L_hard + (1-α) × L_soft

L_hard: 실제 레이블과의 Cross Entropy
L_soft: 교사 출력과의 KL Divergence
α: 가중치 (보통 0.1~0.5)
```
## 증류 유형
| 유형 | 설명 |
|------|------|
| Response-based | 최종 출력 레이어 증류 |
| Feature-based | 중간 특징맵 증류 |
| Relation-based | 데이터 간 관계 증류 |
| Self-Distillation | 같은 모델 내 증류 |
## 장점
| 장점 | 설명 |
|------|------|
| 모델 압축 | 파라미터 수 대폭 감소 |
| 성능 유지 | 교사 모델 성능 근접 |
| 추론 속도 | 빠른 추론 가능 |
| 배포 용이 | 엣지 디바이스 배포 |
## 활용 사례
- BERT → DistilBERT (40% 압축, 97% 성능 유지)
- GPT → 경량 모델
- 이미지 분류 모델 압축
- 온디바이스 AI 배포
