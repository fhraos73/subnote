#정보관리기술사 #디지털서비스 #OpenAPI #API

## 정의
**개방형 프로그래밍 인터페이스, Open API**
- 외부 개발자나 파트너에게 API(Application Programming Interface)를 공개하여 서비스 연동 및 확장을 가능하게 하는 개방형 인터페이스 기술
- 플랫폼 생태계 확장을 위해 표준화된 방식으로 기능과 데이터를 외부에 제공하는 공개 API
## 키워드
* API Gateway, API Manager, 개발자포탈, Cache, Authentication, RESTful, JSON, OAuth
## 암기법
* 게매서 캐인 개커 (Gateway, Manager, Support&Analysis, Cache, 인증, 개발자포탈, 커뮤니티) - 7대 구성요소
## 특징
- 개방성: 외부 개발자에게 API를 공개하여 생태계 확장
- 표준화: RESTful, JSON 등 표준 프로토콜 기반 연동
- 보안 인증: OAuth, API Key 등을 통한 접근 제어
- 생태계 확장: 서드파티 개발자 참여를 통한 플랫폼 가치 증대
## 목적
- 플랫폼 생태계 확장 및 서드파티 개발자 참여 유도
- 서비스 간 연동을 통한 새로운 비즈니스 모델 창출
## 구성요소
- API Gateway: API 호출의 단일 진입점, 라우팅·로드밸런싱·보안 처리
- API Manager Portal: API 등록·관리·버전 관리·정책 설정
- API Support & Analysis: API 사용 모니터링, 분석, 리포팅
- Cache: API 응답 캐싱을 통한 성능 최적화
- Authentication(인증): OAuth, API Key, JWT 기반 접근 제어
- 개발자포탈: API 문서화, 테스트 환경, SDK 제공
- 커뮤니티: 개발자 간 소통, Q&A, 사례 공유 플랫폼
## 구성도
```
[Open API 플랫폼 구성] 게매서 캐인 개커

  외부 개발자 ──요청──▶ API Gateway ──라우팅──▶ 백엔드 서비스
       │                    │                       │
   개발자포탈           Authentication           API 서버
   커뮤니티              Cache                   데이터베이스
       │                    │
       └── API Manager Portal ── API Support & Analysis
           (등록/관리/정책)       (모니터링/분석)
```
## 기출
- 122회 기출
## 연관 토픽
- [[REST, RESTful API 설계 6원칙]] - API 아키텍처 스타일
- [[MSA]] - 마이크로서비스 간 API 연동
- [[OAuth]] - API 인증 프로토콜
- [[클라우드 컴퓨팅]] - 클라우드 API 서비스
