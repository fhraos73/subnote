#AI #LLM #검색증강 #필수

## 정의
검색 기반 생성 증강 기술, RAG
- 환각 현상(Hallucination) 통제를 위해 대규모 언어 모델의 출력을 최적화하여 응답을 생성하기 전에, 최신 학습 데이터 소스 외부의 신뢰할 수 있는 지식 베이스를 참조하여 적절한 문서 검색 및 답변을 생성해 LLM 모델의 정확성과 신뢰성을 향상시키는 프로세스
- Retrieval: 회수, 검색의 의미
## 키워드
* Retrieval, Augmented, Generation, 벡터 DB, 임베딩, 청킹, Function Calling
* Advanced RAG : 인덱싱 구조 최적화, 쿼리 최적화, 리랭킹, 컨텍스트 압축
## 암기법
* RAG = Retrieval(검색) + Augmented(증강) + Generation(생성)
* 검색해서 증강하고 생성한다
## 구성요소
- ==검색기(Retriever)==: 관련 문서 검색 (Dense/Sparse Retrieval)
- ==벡터 DB==: 문서 임베딩 저장 (Pinecone, Chroma, Faiss)
- ==생성기(Generator)==: LLM 기반 답변 생성
- ==청킹(Chunking)==: 문서 분할 전략
- ==임베딩(Embedding)==: 텍스트 벡터화
## 연관 토픽
- [[LLM]] - 대규모 언어 모델
- [[환각 현상(Hallucination)]] - LLM 한계
- [[RIG(Retrieval Interleaved Generation)]] - 검색 인터리브 생성
## 동작 원리
```
┌─────────┐    ┌─────────────┐    ┌─────────┐    ┌─────────┐
│  질의    │ →  │   검색기      │ →  │  문서    │ →  │   LLM   │ → 답변
│ (Query) │    │ (Retriever) │    │ (Docs)  │    │         │
└─────────┘    └─────────────┘    └─────────┘    └─────────┘
                     │ Funtion Calling
                     ▼
              [벡터 데이터베이스]
              (Vector DB)
```
## RAG vs Fine-tuning
| 구분 | RAG | Fine-tuning |
|------|-----|-------------|
| 최신 정보 | 실시간 반영 | 재학습 필요 |
| 비용 | 낮음 | 높음 |
| 환각 | 감소 | 여전히 존재 |
| 출처 | 명확 | 불명확 |
| 도메인 특화 | 문서 추가 | 학습 필요 |
## RAG 파이프라인
1. ==문서 수집==: 지식 베이스 구축
2. ==청킹==: 문서를 적절한 크기로 분할
3. ==임베딩==: 텍스트를 벡터로 변환
4. ==인덱싱==: 벡터 DB에 저장
5. ==검색==: 질의와 유사한 문서 검색
6. ==생성==: 검색 결과 + 질의로 답변 생성
## 고급 RAG 기법
- ==Hybrid Search==: Dense + Sparse 검색 결합
- ==Re-ranking==: 검색 결과 재정렬
- ==Query Expansion==: 질의 확장
- ==Self-RAG==: 자기 검증 RAG
