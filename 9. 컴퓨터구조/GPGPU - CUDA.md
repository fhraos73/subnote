#컴퓨터구조 #GPU #CUDA #병렬처리 #필수 #컴퓨터구조/프로세서
## 정의
GPU를 범용 연산에 활용하는 병렬 컴퓨팅 기술, GPGPU
- GPU(Graphics Processing Unit)를 CPU가 맡고 있는 응용 프로그램들의 계산에 사용할 수 있도록 활용하는 기법
- Blackwell(NVIDIA 차세대 아키텍처), Rubin(차차세대 아키텍처)
## 키워드
* CUDA, OpenCL, OpenACC, 부동소수점 연산, SM/SP, 병렬처리, Blackwell, Rubin
## 암기법
* "부문쓰" - 부동소수점 빠름, 문맥교환 빠름, 쓰레드 다수
* "쿠오오C" - CUDA, OpenCL, OpenACC, C++ AMP
## 구성요소/특징/유형
| 구분 | 설명 | 비고 |
| ---- | ---- | ---- |
| CUDA | NVIDIA 전용 병렬 프로그래밍 모델 | SM/SP 구성, 제한된 호환성 |
| OpenCL | 크로노스 그룹, 이기종 시스템 지원 | 애플/AMD/IBM |
| OpenACC | CUDA 추상화, 컴파일러 지시문 기반 | 플랫폼 독립 |
| C++ AMP | MS Visual Studio 이기종 지원 | 람다표현, 병렬반복문 |
## 구성도
```
[CPU] ──요청──▶ [GPGPU 플랫폼]
                    │
        ┌───────────┴───────────┐
        ▼                       ▼
   [CUDA/OpenCL]         [OpenACC/C++ AMP]
        │                       │
        ▼                       ▼
   [GPU SM/SP 코어]        [이기종 프로세서]
   (수천개 병렬 코어)       (CPU+GPU 협업)
```
## 연관 토픽
- [[HBM]] - GPU 메모리 대역폭 확장
- [[뉴로모픽칩(Neuromorphic chip)]] - 차세대 AI 전용 프로세서
- [[캐시 메모리]] - GPU 내 소형 캐시 구성
