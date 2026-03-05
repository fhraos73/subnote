#정보관리기술사 #보안 #OWASP #LLM #AI보안 #정리

## 정의
대규모 언어 모델 10대 보안 취약점, OWASP LLM Top 10
- 대규모 언어 모델(LLM) 기반 애플리케이션에서 발생할 수 있는 상위 10개의 보안 취약점을 기술한 가이드라인
- 2023년 OWASP에서 제정, 2025년 업데이트 버전 발표

## 키워드
* Prompt Injection, Data Poisoning, Model Theft, Sensitive Data Exposure, Supply Chain

## 암기법
* 프민공데부과시벡잘무: (2025 Top10) 프롬프트인젝션, 민감정보공개, 공급망취약점, 데이터중독, 부적절한출력처리, 과도한대행, 시스템프롬프트노출, 벡터임베딩취약점, 잘못된정보, 무제한소비

## 특징
- LLM 특화: 기존 웹 취약점과 다른 AI 고유 위협
- 프롬프트 기반: 입력 조작을 통한 공격 다수
- 데이터 의존: 학습 데이터 품질이 보안에 영향
- 신뢰 문제: AI 출력에 대한 과신 위험

## 목적
- LLM 애플리케이션 보안 인식 제고
- AI 개발자/운영자 보안 가이드라인 제공
- 생성형 AI 서비스 보안 기준 수립

## 구성요소
| 순위 | 취약점 | 설명 |
|------|--------|------|
| LLM01 | Prompt Injection | 프롬프트 조작으로 의도치 않은 동작 유발 |
| LLM02 | Sensitive Information Disclosure | 민감한 정보 공개, 학습 데이터 노출 |
| LLM03 | Supply Chain Vulnerabilities | 공급망 취약점, 모델/플러그인 위험 |
| LLM04 | Data and Model Poisoning | 데이터 및 모델 중독, 학습 데이터 오염 |
| LLM05 | Improper Output Handling | 부적절한 출력 처리, XSS/인젝션 연계 |
| LLM06 | Excessive Agency | 과도한 대행, 자율 행동 위험 |
| LLM07 | System Prompt Leakage | 시스템 프롬프트 노출 |
| LLM08 | Vector and Embedding Weaknesses | 벡터와 임베딩 취약점 |
| LLM09 | Misinformation | 잘못된 정보, 할루시네이션 |
| LLM10 | Unbounded Consumption | 무제한 소비, 리소스 고갈 |

## 구성도
```
[OWASP LLM Top 10 2025]
         │
    ┌────┴────┬────┬────┐
    ▼         ▼    ▼    ▼
[입력 취약점] [데이터 취약점] [출력 취약점] [운영 취약점]
    │            │            │            │
    ▼            ▼            ▼            ▼
[Prompt     [Data         [Output      [Excessive
Injection]  Poisoning]    Handling]    Agency]
    │            │            │            │
[System     [Supply       [Misinfor-   [Unbounded
Prompt      Chain]        mation]      Consumption]
Leakage]
    │
    ▼
[대응방안]
    │
    ├── 입력 검증/필터링
    ├── 출력 검증/제한
    ├── 학습 데이터 검증
    ├── 권한 최소화
    └── 모니터링/감사
```

## 연관 토픽
- [[OWASP Top 10]] - 웹 애플리케이션 보안 취약점
- [[생성형 AI 위협 및 대응방안]] - 생성형 AI 보안
- [[딥러닝 취약점]] - AI/ML 보안 취약점
- [[프롬프트 엔지니어링]] - 프롬프트 설계 및 보안
