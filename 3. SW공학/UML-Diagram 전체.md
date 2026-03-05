#SW공학 #UML #모델링 #필수

## 정의
통합 모델링 언어, UML
- 객체지향 소프트웨어 시스템을 시각적으로 명세화, 구축, 문서화하기 위한 표준 모델링 언어
- OMG(Object Management Group)에서 제정한 표준으로, 구조와 행위를 다양한 다이어그램으로 표현
## 키워드
- Class, Use Case, Sequence, Activity, State Machine
- Component, Deployment, Package, Object
- 구조 다이어그램, 행위 다이어그램
- OMG, 모델링, 시각화, 명세화
## 암기법
- 구조 다이어그램 6개: 클객컴배패복 (Class-Object-Component-Deployment-Package-Composite)
- 행위 다이어그램 7개: 유활상시통타인 (UseCase-Activity-State-Sequence-Communication-Timing-Interaction)
- 핵심 3대: 클유시 (Class-UseCase-Sequence)
## 목적
- 시스템 구조와 행위의 시각적 표현 및 의사소통
- 소프트웨어 설계 문서화 및 개발 가이드 제공
## 구성요소
### 구조 다이어그램(Structure Diagram)
- **Class Diagram(클래스 다이어그램): 클래스 구조와 관계**
- ![[Pasted image 20260130225405.png|200]]
- Object Diagram(객체 다이어그램): 특정 시점의 객체 인스턴스
- Component Diagram(컴포넌트 다이어그램): 컴포넌트 간 의존관계
- Deployment Diagram(배포 다이어그램): 물리적 배치 구조
- **Package Diagram(패키지 다이어그램): 패키지 간 의존관계**
- **Composite Structure Diagram(복합 구조 다이어그램): 내부 구조**
### 행위 다이어그램(Behavior Diagram)
- **Use Case Diagram(유스케이스 다이어그램): 시스템 기능과 액터**
- ![[Pasted image 20260130225357.png|200]]
- **Activity Diagram(활동 다이어그램): 업무 흐름과 제어 흐름**
- ![[Pasted image 20260130225416.png|400]]
- State Machine Diagram(상태 머신 다이어그램): 객체의 상태 전이
- **Sequence Diagram(시퀀스 다이어그램): 시간 순서에 따른 상호작용**
- **Communication Diagram(통신 다이어그램): 객체 간 메시지 교환**
- **Timing Diagram(타이밍 다이어그램): 시간 제약이 있는 상호작용**
- Interaction Overview Diagram(상호작용 개요): 상호작용 흐름
- State Diagram(상태 다이어그램) : 객체 생명주기 동안 겪는 상태변화 표현
- ![[Pasted image 20260130225530.png|400]]
## 구성도
```
┌─────────────────────────────────────────┐
│            UML 2.x                      │
└─────────────────────────────────────────┘
                │
        ┌───────┴────────┐
        ▼                ▼
┌───────────────┐  ┌──────────────┐
│Structure (구조)│  │Behavior(행위)│
└───────────────┘  └──────────────┘
        │                  │
    ┌───┴─────┐        ┌──┴────────┐
    ▼         ▼        ▼           ▼
[Class]   [Component] [UseCase] [Sequence]
[Object]  [Deployment][Activity][StateMachine]
[Package] [Composite] [Communication]
                      [Timing]
                      [Interaction Overview]

[다이어그램 선택 기준]
- 요구분석: Use Case
- 설계: Class, Sequence, State
- 구현: Component, Deployment
- 동적행위: Activity, Sequence, State
```
## 연관 토픽
- [[UML의 관계]] - UML 관계 표현
- [[Class diagram]] - 클래스 다이어그램
- [[Usecase diagram]] - 유스케이스 다이어그램
- [[Sequence diagram]] - 시퀀스 다이어그램
- [[활동 다이어그램]] - 활동 흐름 표현
- [[상태 머신 다이어그램]] - 상태 전이 표현
## 특징
- 표준화: 국제 표준 모델링 언어
- 시각화: 그래픽 표기법 활용
- 다양성: 13개 다이어그램 제공
- 의사소통: 공통 언어로 소통 촉진
