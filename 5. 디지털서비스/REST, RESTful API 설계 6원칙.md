#정보관리기술사 #디지털서비스 #REST #RESTful #API #정의
## 정의
**분산 하이퍼미디어 SW 아키텍처, REST**
- REST(Representational State Transfer): 분산 하이퍼미디어 시스템을 위한 SW 아키텍처 스타일로, 부가적인 전송레이어 없이 전송하는 경량 HTTP 프로토콜 기반 기술
- 자원을 URI로 표현하고 HTTP Method로 행위를 정의하여 상태를 전달하는 웹 서비스 아키텍처 스타일
## 키워드
* URI, HTTP Method, Representations, Stateless, Cacheable, PUT, GET, POST, DELETE, WebDAV
## 암기법
* 유무캐자클계 (유니폼 인터페이스, 무상태, 캐시, 자체표현, 클라이언트-서버, 계층형) - 6대 특징
## 특징
- 유니폼 인터페이스: 통일되고 한정적인 인터페이스로 조작하는 아키텍처 스타일
- 무상태성(Stateless): 서버가 클라이언트 상태를 저장하지 않아 확장성 확보
- 캐시 가능(Cacheable): HTTP 캐싱 기능 활용으로 응답 성능 향상
- 자체 표현 구조: 메시지만으로 API 의미를 이해할 수 있는 자기 서술적 구조
## REST 3대 요소
- 자원(Resource): URI로 식별되는 모든 자원
- 행위(Verb): HTTP Method(PUT, GET, POST, DELETE)로 표현
- 표현(Representations): JSON, XML 등 자원의 상태 표현
## RESTful API 설계 6원칙
- Uniform Interface: 통일된 인터페이스로 플랫폼 독립적 상호작용
- Stateless: 각 요청은 독립적이며 서버에 상태 저장 없음
- Cacheable: 응답 데이터의 캐싱 가능 여부 명시
- Client-Server: 클라이언트와 서버의 역할 분리
- Layered System: 보안, 로드밸런싱, 암호화 등 계층형 구조
- Code on Demand(선택): 서버에서 클라이언트로 실행 코드 전송
## 디자인 가이드
- URI는 정보의 자원을 표현 (명사 사용)
- 자원에 대한 행위는 HTTP Method로 표현
- PUT: 자원 수정(Update)
- GET: 자원 조회(Read)
- POST: 자원 생성(Create)
- DELETE: 자원 삭제(Delete)
- WebDAV extension 활성화
## 구성도
```
[REST 아키텍처]

  Client ──HTTP Request──▶ Server
    │                        │
  URI(자원식별)          자원(Resource)
  HTTP Method(행위)      비즈니스 로직
  Representations(표현)  데이터 저장소

[HTTP Method ↔ CRUD]
  POST   → Create (생성)
  GET    → Read   (조회)
  PUT    → Update (수정)
  DELETE → Delete (삭제)

[6대 원칙]
  Uniform Interface ─ Stateless ─ Cacheable
  Client-Server ─ Layered System ─ Code on Demand
```
## 연관 토픽
- [[Open API]] - 공개 API 인터페이스
- [[MSA]] - 마이크로서비스 간 통신
- [[HTTP]] - 전송 프로토콜
- [[JSON]] - 데이터 표현 형식
