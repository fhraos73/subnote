#AI #딥러닝 #이미지처리 #필수

## 정의
이미지 특징 추출에 특화된 합성곱 신경망, CNN
- 고차원 특징 추출 분류를 위해 기존 신경망에 다계층의 합성곱 계층을 추가한 딥러닝 모델
- 이미지, 영상 등 시각적 데이터 처리에 최적화된 신경망 구조
## 키워드
* Convolution, Pooling, Filter, Feature Map, Stride, Padding
## 암기법
* CNN 구조: ==입합풀완출== (입력, 합성곱, 풀링, 완전연결, 출력)
## 구성요소
```
[입력층] → [합성곱층] → [ReLU] → [풀링층] → [완전연결층] → [출력층]
  Input Convolution  ReLU   Pooling Fully Connecte Output
```
### 핵심 계층
- ==합성곱층(Convolution Layer)==: 필터(커널)를 이용한 특징 추출
- ==풀링층(Pooling Layer)==: 특징맵 크기 축소 (Max/Average Pooling)
- ==완전연결층(FC Layer)==: 추출된 특징 기반 분류
### 주요 개념
- ==필터(Filter/Kernel)==: 특징 추출을 위한 가중치 행렬
- ==스트라이드(Stride)==: 필터 이동 간격
- ==패딩(Padding)==: 입력 크기 유지를 위한 테두리 추가
- ==특징맵(Feature Map)==: 합성곱 연산 결과
## 연관 토픽
- [[RNN]] - 순환 신경망
- [[LSTM]] - 장단기 메모리
- [[GAN (Generative Adversarial Network)]] - 생성적 적대 신경망
## 주요 CNN 아키텍처
| 모델         | 특징                       |
| ---------- | ------------------------ |
| LeNet      | 최초의 CNN (손글씨 인식)         |
| AlexNet    | ImageNet 우승, ReLU 도입     |
| VGGNet     | 깊은 네트워크 (16/19층)         |
| ResNet     | 잔차 연결(Skip Connection)   |
| R-CNN      | 객체 탐지 (Region-based CNN) |
| Fast R-CNN | 빠르게 R-CNN                |
## 활용 분야
- 이미지 분류 (Image Classification)
- 객체 탐지 (Object Detection): YOLO, R-CNN
- 얼굴 인식 (Face Recognition)
- 의료 영상 분석
