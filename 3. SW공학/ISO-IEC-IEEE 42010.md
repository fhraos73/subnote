#SW공학 #아키텍처 #표준 #필수 #SW공학/SW_아키텍처

## 정의
아키텍처 기술 국제표준, ISO/IEC/IEEE 42010
- 시스템과 소프트웨어의 아키텍처 기술(Architecture Description)을 위한 국제 표준
- 아키텍처 관점(View), 뷰포인트(Viewpoint), 이해관계자 관심사(Concern)를 체계적으로 정의
## 키워드
- Architecture Description, Stakeholder, Concern
- Viewpoint, View, Model Kind, Correspondence
- IEEE 1471, ISO 42010
## 암기법
- 4+1 view
- 스콘뷰포모 (Stakeholder-Concern-View-Viewpoint-Model)
- AD의 핵심: 누가(Stakeholder) 무엇을(Concern) 어떻게(Viewpoint/View)
## 목적
- 아키텍처 문서화의 표준 프레임워크 제공
- 이해관계자 간 효과적인 의사소통 지원

## 구성요소
| 구성요소                         | 설명                              |
| ---------------------------- | ------------------------------- |
| **Entity of Interest**       | 아키텍처 기술 대상 시스템 또는 조직            |
| **Stakeholder**              | 시스템과 관련된 이해관계자                  |
| **Concern**                  | 이해관계자가 가지는 관심사항 (성능, 보안, 확장성 등) |
| **Viewpoint**                | Concern을 해결하기 위한 아키텍처 관점 정의     |
| **View**                     | Viewpoint에 따라 표현된 아키텍처 구조       |
| **Architecture Model**       | View를 구성하는 모델 요소                |
| Architecture Description(AD) | 아키텍처를 문서화한 산출물                  |
| Model Kind(모델 종류)            | 뷰를 구성하는 모델의 유형                  |


## 구성도
```
┌─────────────────────────────────────────┐
│    System of Interest (관심 시스템)      │
└────────────┬────────────────────────────┘
             │ has
             ▼
┌──────────────────────────────────────────┐
│  Architecture Description (AD)           │
└──────────────────────────────────────────┘
             │
     ┌───────┼───────┐
     ▼       ▼       ▼
┌─────────┐ ┌─────────┐ ┌─────────┐
│Viewpoint│ │Viewpoint│ │Viewpoint│
└────┬────┘ └────┬────┘ └────┬────┘
     │           │           │
     └───────┬───┴───────┬───┘
             ▼           ▼
         ┌──────┐    ┌──────┐
         │ View │◄───┤ View │
         └──────┘    └──────┘
             │
             ▼
     ┌───────────────┐
     │  Stakeholder  │
     │  + Concerns   │
     └───────────────┘
```

![[Pasted image 20260130222032.png]]
## 연관 토픽
- [[SW Architecture]] - 소프트웨어 아키텍처 기본 개념
- [[SW Architecture 평가]] - 아키텍처 평가 방법론
- [[UML-Diagram 전체]] - 아키텍처 표현 도구
## 특징
- 표준화: 국제 표준 프레임워크 제공
- 다관점: 다양한 이해관계자 관점 수용
- 체계성: 명확한 개념 모델과 용어 정의
- 일관성: 아키텍처 기술의 일관된 방법론
