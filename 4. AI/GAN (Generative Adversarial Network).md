#AI #딥러닝 #생성모델 #필수

## 정의
생성자와 판별자가 경쟁하며 학습하는 생성 모델, GAN
- 생성자(Generator)와 판별자(Discriminator)가 서로 경쟁하는 과정을 통해 정보를 학습하는 대표적 비지도학습
- 실제와 구분하기 어려운 가짜 데이터를 생성하는 딥러닝 모델
## 키워드
* Generator, Discriminator, 적대적 학습, DCGAN, 비지도학습
* Min-Max
## 암기법
* GAN = Generator(생성) + Adversarial(적대) + Network(네트워크)
* 생성자 vs 판별자 = 위조범 vs 경찰
## 연관 토픽
- [[오토인코더(Autoencoder)/VAE]] - 생성 모델
- [[딥페이크]] - 영상 합성
- [[머신러닝 학습과정에서의 적대적 공격]] - 보안
## 구조
```
┌─────────────┐         ┌─────────────┐
│   노이즈    │         │  실제 데이터 │
│   (z)       │         │             │
└──────┬──────┘         └──────┬──────┘
       │                       │
       ▼                       │
┌─────────────┐                │
│  생성자(G)  │                │
│  Generator  │                │
└──────┬──────┘                │
       │                       │
       ▼                       ▼
┌─────────────────────────────────┐
│        판별자(D)                 │
│        Discriminator            │
│   (진짜/가짜 판별)               │
└─────────────────────────────────┘
```
## 학습 원리
- ==생성자(Generator)==: 노이즈로부터 가짜 데이터 생성, 판별자를 속이려 함
- ==판별자(Discriminator)==: 진짜/가짜 데이터 구분, 생성자를 탐지하려 함
- ==적대적 학습==: 두 네트워크가 경쟁하며 성능 향상 (Min-Max Game)
## GAN 변형 모델
| 모델 | 특징 |
|------|------|
| ==DCGAN== | Fully Connected Layer 제거, Convolution Layer와 배치정규화 사용 |
| ==Defense GAN== | 적대적 공격 방어를 위한 GAN |
| CGAN | 조건부 생성 (Conditional GAN) |
| StyleGAN | 고해상도 이미지 생성 |
| CycleGAN | 이미지 스타일 변환 |
## DCGAN(Deep Convolutional GAN)
- GAN의 Fully Connected Layer를 제거하고 Convolution Layer와 배치정규화 구조를 사용
- 안정적인 학습이 가능한 알고리즘
## Defense GAN
- 적대적 훈련(Adversarial Training) 및 방어 기법
- 적대적 공격으로부터 모델을 보호하는 GAN 기반 방어 메커니즘
## 활용 분야
- 이미지 생성/복원
- 딥페이크 (얼굴 합성)
- 데이터 증강
- 초해상도 복원 (SRGAN)
