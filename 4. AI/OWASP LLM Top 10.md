#AI #보안 #LLM

## 정의
LLM 애플리케이션의 주요 보안 취약점 목록, OWASP LLM Top 10
- OWASP(Open Web Application Security Project)에서 발표한 LLM 애플리케이션의 10대 보안 위협
- LLM 기반 시스템 개발 시 고려해야 할 핵심 보안 위험 요소
- **2025년 버전**: 2023년 대비 항목 변경 및 순위 조정 (RAG, 에이전트 등 신기술 반영)
## 키워드
* OWASP, Prompt Injection, Data Poisoning, RAG Security, Unbounded Consumption, LLM Security
## 암기법
* **프민공데부 과시벡허무**: 프롬프트-민감정보-공급망-데이터오염-부적절출력-과도한위임-시스템프롬프트-벡터-허위정보-무제한소비
* 2025 신규: **시스템 프롬프트 유출**, **벡터 및 임베딩 취약점** (RAG 보안 강화)
## 연관 토픽
- [[LLM]] - 대규모 언어 모델
- [[RAG]] - 검색 증강 생성
- [[머신러닝 학습과정에서의 적대적 공격]] - 적대적 공격
- [[AI 거버넌스 (AI Governance)]] - AI 거버넌스
- [[프롬프트 엔지니어링]] - 프롬프트 설계
## OWASP LLM Top 10 (2025)
| 순위  | 취약점 (영문)                        | 취약점 (한글)     | 설명                           |
| --- | ------------------------------- | ------------ | ---------------------------- |
| 1   | ==Prompt Injection==            | 프롬프트 인젝션     | 악의적 프롬프트로 모델 동작 조작           |
| 2   | ==Sensitive Info Disclosure==   | 민감 정보 유출     | PII, 기밀 데이터 무단 노출            |
| 3   | ==Supply Chain==                | 공급망          | 타사 모델/데이터/컴포넌트 취약점           |
| 4   | ==Data and Model Poisoning==    | 데이터 및 모델 오염  | 학습/미세조정 데이터 조작, 백도어 삽입       |
| 5   | ==Improper Output Handling==    | 부적절한 출력 처리   | 출력 검증 없이 다운스트림 전달 (XSS 등)    |
| 6   | ==Excessive Agency==            | 과도한 위임       | LLM에 과도한 권한/자율성 부여           |
| 7   | ==System Prompt Leakage==       | 시스템 프롬프트 유출  | 시스템 프롬프트 내 민감정보 노출           |
| 8   | ==Vector & Embedding Weakness== | 벡터 및 임베딩 취약점 | RAG 시스템의 접근 제어/오염 문제         |
| 9   | ==Misinformation==              | 허위 정보        | 환각(Hallucination), 잘못된 정보 생성 |
| 10  | ==Unbounded Consumption==       | 무제한 소비       | DoS, 지갑 공격(DoW), 모델 추출       |
## 2025 vs 2023 버전 변경사항
| 구분        | 2023 버전                       | 2025 버전                    |
| ----------- | ------------------------------- | ---------------------------- |
| 신규 추가   | -                               | 시스템 프롬프트 유출 (LLM07) |
| 신규 추가   | -                               | 벡터 및 임베딩 취약점 (LLM08)|
| 명칭 변경   | Training Data Poisoning         | Data and Model Poisoning     |
| 명칭 변경   | Model DoS                       | Unbounded Consumption        |
| 삭제        | Insecure Plugin Design          | (Excessive Agency로 통합)    |
| 삭제        | Overreliance                    | (Misinformation으로 재정의)  |
| 삭제        | Model Theft                     | (Unbounded Consumption 포함) |
## 주요 취약점 상세
### LLM01: Prompt Injection (프롬프트 인젝션)
- **직접 인젝션**: 사용자가 직접 악의적 프롬프트 입력하여 지침 우회
- **간접 인젝션**: 외부 소스(웹사이트, 파일)를 통해 악의적 명령 주입
- **대응**: 입력 검증, 권한 제어, 외부 콘텐츠 분리, 적대적 테스트
### LLM02: Sensitive Info Disclosure (민감 정보 유출)
- PII, 재무정보, 독점 알고리즘 등 노출 위험
- 학습 데이터 내 민감정보가 출력에 반영
- **대응**: 데이터 정제(Sanitization), 차등 개인정보 보호, 연합 학습
### LLM03: Supply Chain (공급망)
- 취약한 타사 패키지, 오래된 모델, 취약한 LoRA 어댑터
- **대응**: SBOM 관리, 모델 출처 검증, AI 레드팀 평가
### LLM04: Data and Model Poisoning (데이터 및 모델 오염)
- 사전학습/미세조정/임베딩 데이터 조작
- 백도어 삽입, 편향 주입
- **대응**: 데이터 출처 추적, 이상 징후 탐지, DVC(Data Version Control)
### LLM05: Improper Output Handling (부적절한 출력 처리)
- LLM 출력을 검증 없이 시스템 쉘, DB, 브라우저에 전달
- XSS, SQL Injection, RCE 유발 가능
- **대응**: 제로 트러스트, 출력 인코딩, CSP 적용
### LLM06: Excessive Agency (과도한 위임)
- **과도한 기능**: 불필요한 확장 기능 제공
- **과도한 권한**: 최소 권한 원칙 미적용
- **과도한 자율성**: 사람의 승인 없이 위험 작업 수행
- **대응**: 확장 기능 최소화, 권한 최소화, 인적 승인 필수
### LLM07: System Prompt Leakage (시스템 프롬프트 유출) ⭐ 신규
- 시스템 프롬프트에 자격 증명, 내부 규칙, 권한 구조 포함 시 유출 위험
- **대응**: 민감 데이터 분리, 외부 가드레일 구현
### LLM08: Vector & Embedding Weakness (벡터 및 임베딩 취약점) ⭐ 신규
- RAG 시스템의 무단 접근, 데이터 오염, 임베딩 역추적 공격
- 멀티테넌트 환경에서 교차 컨텍스트 정보 유출
- **대응**: 세분화된 접근 제어, 데이터 검증 파이프라인
### LLM09: Misinformation (허위 정보)
- **환각(Hallucination)**: 사실처럼 보이는 허구 콘텐츠 생성
- 과도한 신뢰로 인한 잘못된 의사결정
- **대응**: RAG 활용, 교차 검증, 자동 검증 메커니즘
### LLM10: Unbounded Consumption (무제한 소비)
- **DoS**: 대량 요청으로 서비스 거부
- **DoW(Denial of Wallet)**: 클라우드 비용 폭증 유발
- **모델 추출**: API를 통한 모델 복제
- **대응**: 속도 제한, 자원 할당 관리, 워터마킹
## 보안 대응 전략
| 영역     | 대응 방안                                       |
| -------- | ----------------------------------------------- |
| 입력     | 프롬프트 검증, 필터링, 샌드박싱                 |
| 모델     | 접근 제어, 모니터링, 출처 검증                  |
| 출력     | 인코딩, CSP, 제로 트러스트                      |
| 데이터   | 암호화, 익명화, DVC                             |
| 공급망   | SBOM, 검증된 모델/플러그인 사용                 |
| RAG      | 권한 인식 벡터 DB, 데이터 검증                  |
| 권한     | 최소 권한 원칙, 인적 승인                       |
