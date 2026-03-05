#AI #딥러닝 #신경망 #필수

## 정의
신경망의 비선형성을 부여하는 함수, 활성화 함수
- 인간의 시냅스(Synapse)에 전달된 활동전위 신호가 최소의 자극값을 초과할 때 활성화되어 다음 뉴런으로 전달되는 과정을 구현한 함수
- ==신경망에서 입력의 신호가 활성화 조건인지 판단하고 비선형 변환 하는 함수==
- 신경망 학습 모델의 input 값에서 output 값을 도출할 때 비선형 변환을 수행
## 키워드
* Sigmoid, Tanh, ReLU, Softmax, 비선형성, 기울기 소실
## 암기법
* ==시타렐소== (Sigmoid, Tanh, ReLU, Leaky ReLU, Softmax)
## 연관 토픽
- [[경사하강법]] - 학습 최적화
- [[과적합(Overfitting) 문제]] - 모델 일반화
- [[CNN]] - 합성곱 신경망
## 주요 활성화 함수
| 함수 | 수식 | 특징 | 문제점 |
|------|------|------|--------|
| ==Si==gmoid | σ(x)=1/(1+e^-x) | 출력 0~1, 확률 해석 | 기울기 소실 |
| ==Ta==nh | tanh(x) | 출력 -1~1, 중심 0 | 기울기 소실 |
| ==Re==LU | max(0,x) | 계산 효율, 희소성 | Dying ReLU |
| ==Le==aky ReLU | max(0.01x,x) | 음수 기울기 0.01 | - |
| ==So==ftmax | 출력층 분류 | 다중 클래스 확률 | - |
## 선택 기준
- ==은닉층==: ReLU 계열 (ReLU, Leaky ReLU, ELU)
- ==출력층(분류)==: Softmax (다중 클래스), Sigmoid (이진 분류)
- ==출력층(회귀)==: Linear (항등 함수)
## 기울기 소실 문제 해결
- ReLU 사용: 양수 영역에서 기울기 1 유지
- 배치 정규화(Batch Normalization): 입력 분포 정규화
- 잔차 연결(Residual Connection): Skip Connection 활용
