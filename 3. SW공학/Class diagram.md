#SW공학 #UML #구조다이어그램 #필수

## 정의
클래스 구조와 관계 표현, 클래스 다이어그램
- 시스템의 정적 구조를 표현하는 UML 다이어그램으로, 클래스의 속성, 메서드, 관계를 시각화
- 객체지향 설계의 핵심 산출물로, 시스템의 구조와 클래스 간 관계를 명확히 정의
## 키워드
- Class, Attribute, Operation, Visibility
- Association, Inheritance, Interface
- Static Structure, Object-Oriented Design
- public(+), private(-), protected(#), packagr (~)
## 암기법
- 클래스 3요소: 이름-속성-메서드
- 가시성: 퍼프프패 (+public, #protected, -private, ~package)
- 관계: 연집합의일실 (연관-집합-합성-의존-일반화-실체화)
## 목적
- 시스템의 정적 구조 설계 및 문서화
- 클래스 간 관계 정의로 객체지향 설계 가이드 제공
## 구성요소
- Class(클래스): 속성(Attribute)과 메서드(Operation)를 가진 객체의 템플릿
- Attribute(속성): 클래스가 가지는 데이터 필드
- Operation(메서드): 클래스가 수행하는 기능/행위
- Visibility(가시성): public(+), private(-), protected(#), package(~)
- Relationship(관계): 연관, 집합, 합성, 의존, 일반화, 실체화
- Abstract Class(추상 클래스): 인스턴스화 불가, 이탤릭체 표기
- Interface(인터페이스): 메서드 명세만 정의, interface 스테레오타입
- Multiplicity(다중성): 관계의 개수 표현
## 구성도
```
┌─────────────────────────────┐
│       ClassName             │  ← 클래스명
├─────────────────────────────┤
│ - attribute1: Type          │  ← 속성
│ # attribute2: Type          │     (-:private, #:protected, +:public)
│ + attribute3: Type          │
├─────────────────────────────┤
│ + operation1(): ReturnType  │  ← 메서드
│ - operation2(param): void   │
└─────────────────────────────┘

[예시: 도서관 시스템]

┌──────────────┐
│   Library    │
├──────────────┤
│ - name       │
│ - address    │
├──────────────┤
│ + open()     │
│ + close()    │
└──────┬───────┘
       │ 1
       │ has
       │ *
       ▼
┌──────────────┐      ┌──────────────┐
│                    Book                   │  ◇───│   Member     │
├──────────────┤ borrow├──────────────┤
│ - title      │  *  * │ - memberID   │
│ - author     │◄─────►│ - name       │
│ - ISBN       │      │              │
├──────────────┤      ├──────────────┤
│ + borrow()   │      │ + register() │
│ + return()   │      │ + borrow()   │
└──────────────┘      └──────────────┘
       △
       │ inherits
       │
┌──────┴───────┐
│  EBook       │
├──────────────┤
│ - fileSize   │
│ - format     │
├──────────────┤
│ + download() │
└──────────────┘
```
## 연관 토픽
- [[UML-Diagram 전체]] - UML 개요
- [[UML의 관계]] - 클래스 관계 표현
- [[객체지향 설계의 원리]] - 설계 원칙
## 특징
- 정적 모델링: 시스템 구조 표현
- 상세성: 속성과 메서드 명시
- 관계 표현: 다양한 관계 시각화
- 설계 중심: 구현 전 설계 도구
