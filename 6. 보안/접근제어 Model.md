#정보관리기술사 #보안 #접근제어 #보안모델 #정리 #보안/인증/접근제어

## 정의
정보 흐름 및 접근 권한 제어 보안 모델, 접근제어 Model
- 정보시스템의 기밀성, 무결성을 보장하기 위해 주체와 객체 간의 접근 권한을 수학적으로 정의한 보안 모델
- Bell-LaPadula(기밀성), Biba(무결성), Clark-Wilson(무결성), Access Matrix 등

## 키워드
* Bell-LaPadula, Biba, Clark-Wilson, Access Matrix, 기밀성, 무결성, NRU, NWD

## 암기법
* 벨비클액: (모델) Bell-LaPadula, Biba, Clark-Wilson, Access Matrix
* NRU NWD: (Bell-LaPadula) No Read Up, No Write Down
* NRD NWU: (Biba) No Read Down, No Write Up
* BLP 기밀성보장, NRU
* BIBA: 무결성보장, 
* Clark-wilson: 금융권 권한 데이터 무결성
	* TP(Transaction Procedure), IVP(Integrity Verification Procedure)
	* CDI(Constrained Data Item)

## 특징
- 수학적 모델: 형식적 검증 가능
- 정책 기반: 보안 정책의 수학적 표현
- 상호 보완: 기밀성/무결성 모델 조합 사용
- 실무 적용: 군사/금융 시스템 등 적용

## 목적
- 정보 흐름의 체계적 통제
- 기밀성 또는 무결성 보장
- 보안 정책의 형식적 검증

## 구성요소
| 모델 | 목적 | 규칙 | 설명 |
|------|------|------|------|
| Bell-LaPadula | 기밀성 | NRU (No Read Up) | 상위 등급 읽기 금지 |
| Bell-LaPadula | 기밀성 | NWD (No Write Down) | 하위 등급 쓰기 금지 |
| Biba | 무결성 | NRD (No Read Down) | 하위 등급 읽기 금지 |
| Biba | 무결성 | NWU (No Write Up) | 상위 등급 쓰기 금지 |
| Clark-Wilson | 무결성 | CDI/UDI | 제약/비제약 데이터 항목 |
| Clark-Wilson | 무결성 | TP/IVP | 변환/검증 절차 |
| Access Matrix | 권한관리 | ACL/CL | 접근 권한 매트릭스 |

## 구성도
```
[접근제어 보안 모델]
         │
    ┌────┴────┬────────────┐
    ▼         ▼            ▼
[기밀성]   [무결성]     [권한관리]
    │         │            │
    ▼         ▼            ▼
[Bell-     [Biba]      [Access
LaPadula]  [Clark-     Matrix]
           Wilson]
    │         │
    ▼         ▼
[NRU/NWD]  [NRD/NWU]
    │         │
    ▼         ▼
[상위읽기X] [하위읽기X]
[하위쓰기X] [상위쓰기X]

[Bell-LaPadula 예시]
Top Secret ──▶ 읽기O / 쓰기X
     ↑
  Secret ────▶ 읽기O / 쓰기O
     ↑
Confidential ▶ 읽기X / 쓰기O
```

## 연관 토픽
- [[접근제어(AC)]] - 접근제어 기본 개념
- [[MAC]] - 강제적 접근제어
- [[RBAC]] - 역할 기반 접근제어
- [[제로 트러스트]] - 무신뢰 기반 보안 모델
