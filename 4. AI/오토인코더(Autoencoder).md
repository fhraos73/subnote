#AI #딥러닝 #생성모델 #필수

## 정의
입력을 압축하고 복원하는 비지도학습 신경망, 오토인코더
- 입력 데이터를 저차원 잠재 공간(Latent Space)으로 인코딩한 후 다시 원본으로 디코딩하는 신경망
- 차원 축소, 특징 추출, 데이터 생성에 활용
## 키워드
* Encoder, Decoder, Latent Space, VAE, 재구성, 비지도학습
## 암기법
* AE = 압축(Encode) + 복원(Decode)
* VAE = 확률적 AE (생성 가능)
## 구성요소
- ==인코더(Encoder)==: 입력을 저차원 잠재 공간으로 압축
- ==잠재 공간(Latent Space)==: 압축된 표현 (Bottleneck)
- ==디코더(Decoder)==: 잠재 표현을 원본으로 복원
- ==손실 함수==: 재구성 오차 (MSE, BCE)
## 연관 토픽
- [[GAN (Generative Adversarial Network)]] - 생성적 적대 신경망
- [[PCA(주성분분석)]] - 차원 축소
- [[딥페이크]] - 영상 합성
## 구조
```
┌─────────┐    ┌─────────┐    ┌─────────┐
│  입력    │ →  │  잠재    │ →  │  출력    │
│   X     │    │  공간    │    │   X'    │
│         │    │   z     │    │         │
└─────────┘    └─────────┘    └─────────┘
     │              │              │
     ▼              ▼              ▼
 [인코더]      [Bottleneck제지]  [디코더]
  Encoder                      Decoder
```
## 오토인코더 유형
| 유형 | 특징 |
|------|------|
| Vanilla AE | 기본 오토인코더 |
| ==Denoising AE== | 노이즈 제거 학습 |
| ==Sparse AE== | 희소 표현 학습 |
| ==VAE== | 확률적 잠재 공간 |
| Contractive AE | 로버스트 표현 학습 |
## VAE(Variational Autoencoder)
- 잠재 공간을 확률 분포로 모델링 (평균, 분산)
- 새로운 데이터 생성 가능 (생성 모델)
- KL Divergence + 재구성 오차 손실 함수
- 연속적인 잠재 공간으로 보간(Interpolation) 가능
## AE vs VAE vs GAN
| 구분 | Autoencoder | VAE | GAN |
|------|-------------|-----|-----|
| 목적 | 재구성 | 생성 | 생성 |
| 잠재공간 | 결정적 | 확률적 | - |
| 학습 | 재구성 오차 | ELBO | 적대적 |
| 출력 품질 | 흐릿함 | 흐릿함 | 선명함 |
## 활용 분야
- 이미지 노이즈 제거 (Denoising)
- 이상 탐지 (Anomaly Detection)
- 차원 축소 (Dimensionality Reduction)
- 데이터 생성 (VAE)
