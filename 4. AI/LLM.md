#AI #자연어처리 #생성AI #필수

## 정의
대규모 파라미터를 가진 언어 모델, LLM
- 초거대 언어모델로 GPT-3.5, GPT-4 등 수십억~수천억 개의 파라미터를 가진 언어 모델
- 지도학습, 강화학습, RLHF(Reinforcement Learning from Human Feedback) 알고리즘으로 학습
## 키워드
* GPT, BERT, RLHF, Transformer, 파라미터, 토큰
## 암기법
* LLM = Large(대규모) + Language(언어) + Model(모델)
## 주요 LLM 모델
| 모델 | 개발사 | 특징 |
|------|--------|------|
| GPT-4 | OpenAI | 멀티모달, 추론 능력 |
| Claude | Anthropic | 안전성 중시 |
| Gemini | Google | 멀티모달 통합 |
| LLaMA | Meta | 오픈소스 |
| DeepSeek | DeepSeek | MOE, MLA 기반 |
## 학습 과정
```
[사전학습] → [지도학습 미세조정] → [RLHF] → [배포]
Pre-training   Supervised         Human      Deployment
인코딩/디코딩     Fine-tuning        Feedback
```
### RLHF(Reinforcement Learning from Human Feedback)
- 인간 피드백 기반 강화학습
- 보상 모델(Reward Model) 학습 후 정책 최적화
- 유해 출력 감소, 유용성 향상
## LLM 한계 및 해결
| 한계 | 해결 방안 |
|------|-----------|
| 환각 현상(Hallucination) | RAG, 사실 검증 |
| 최신 정보 부재 | RAG, 실시간 검색 |
| 토큰 제한 | 컨텍스트 확장, 압축 |
| 비용 | sLLM, 양자화 |
## 관련 기술
- ==RAG==: 검색 증강 생성
- ==파인튜닝==: 도메인 특화 학습
- ==프롬프트 엔지니어링==: 효과적인 질의 설계
- ==COT==: 단계별 추론
## 연관 토픽
- [[sLLM]] - 경량화 언어모델
- [[트랜스포머(Transformer)]] - 기반 아키텍처
- [[RAG(Retrieval Augmented Generation)/검색 증강 생성 AI]] - 검색 증강
- [[환각 현상(Hallucination)]] - LLM 한계
