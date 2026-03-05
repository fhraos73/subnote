#SW공학 #아키텍처 #필수

## 정의
시스템의 기본 구조와 설계원칙, 소프트웨어 아키텍처
- 소프트웨어 시스템의 구조, 구성요소, 상호작용 및 설계 원칙을 정의하는 청사진
- 품질속성(성능, 보안, 확장성)을 만족시키기 위한 시스템의 근본적인 조직과 구조
## 키워드
- Component, Connector, Configuration
- 4+1 View, IEEE 42010, SAD
## 암기법
- **4+1**: 유논프구배 (UseCase-Logical-Process-Implementation-Physical)
## 목적
- Stakeholder 간 관점 조율, 시스템 최적화
- 요구사항 간 충돌 조정 및 우선순위 결정
## 구성요소
| 구성요소 | 설명 |
|---------|------|
| Component | 시스템의 기능적 단위 |
| Connector | 컴포넌트 간 통신 메커니즘 |
| Configuration | 컴포넌트/연결자 배치 구조 |
## 연관 토픽
- [[ISO-IEC-IEEE 42010]] - 아키텍처 기술 표준
- [[SW Architecture 평가]] - ATAM, CBAM
## 특징
- 간략성: 이해하고 추론할 정도의 간결성
- 추상화: 복잡도 관리를 위한 추상적 표현
- 가시성: 시스템의 청사진(Blue Print)
## 4+1 View
| View | 설명 |
|------|------|
| UseCase | 외부 사용자 관점 |
| Logical | 논리적 구조와 행위 |
| Process | Non-functional 요구사항 |
| Implementation | 독립 실행 컴포넌트 |
| Physical | HW/SW 배치 |
