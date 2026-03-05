#정보관리기술사 #디지털서비스 #자동차안전등급 #필수 #정리

## 정의
**차량 기능 안전 위험도 등급, ASIL(Automotive Safety Integrity Level)**
- ==ISO 26262==에서 정의한 자동차 환경에 맞춘 SIL 레벨로, ==심각도(S), 노출가능성(E), 제어가능성(C)==을 기반으로 위험도를 분류하는 안전 등급 체계
- QM(품질관리)부터 ASIL A~D까지 5단계로 차량 E/E 시스템의 안전 무결성 수준을 결정
## 키워드
* ASIL A~D, QM, 심각도(Severity), 노출도(Exposure), 통제가능성(Controllability), MC/DC, Walk-Through
## 암기법
* 심노통 (심각도, 노출도, 통제가능성)
## 특징
- 3가지 평가요소: 심각도(Severity), 노출도(Exposure), 통제가능성(Controllability)
- 등급 구분: QM(최저) → ASIL A → B → C → D(최고) 5단계
- 등급별 검증 차등: 등급이 높을수록 엄격한 검증 기법 요구
- ASIL D 최고 등급: MC/DC(Modified Condition/Decision Coverage) 테스트 필수
## 목적
- 차량 전기전자 시스템의 위험도를 정량적으로 분류하여 안전 요구사항 수준 결정
- 등급에 따른 적절한 개발 프로세스 및 검증 기법 적용
## 구성요소
- 심각도(Severity): S0(무상해) ~ S3(생명위협) - 4단계
- 노출도(Exposure): E0(미발생) ~ E4(매우높음) - 5단계
- 통제가능성(Controllability): C0(통제가능) ~ C3(통제불가) - 4단계
- 등급: QM, ASIL A, ASIL B, ASIL C, ASIL D
## 검증기법
- ASIL A, B 등급: Walk-Through 비공식 검증
- ASIL C 등급: Semi-formal 검증 권고
- ASIL D 등급: Formal 검증 필수, ==MC/DC(Modified Condition/Decision Coverage)== 테스트 필수
## 구성도
```
[ASIL 결정 매트릭스]
  심각도(S) × 노출도(E) × 통제가능성(C) → ASIL 등급

  QM ← ASIL A ← ASIL B ← ASIL C ← ASIL D
  (최저)                              (최고)

[검증 수준]
  A,B: Walk-Through(비공식)
  C  : Semi-formal(준공식)
  D  : Formal + MC/DC(공식)
```
## 연관 토픽
- [[ISO 26262]] - 자동차 기능안전 표준
- [[IEC 61508]] - 모(母) 기능안전 표준
- [[기능 안전 표준]] - 분야별 기능 안전
- [[Smart Car(자율주행)]] - 자율주행 안전
