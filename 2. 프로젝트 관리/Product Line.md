#프로젝트관리 #개발모델

## 정의
자산 재사용을 통해 유사 제품군을 효율적으로 개발하는 기법, 프로덕트 라인
- 공통된 핵심 자산(Core Assets)을 기반으로 특정 시장이나 목적에 맞는 제품들을 전략적으로 생산
- 대량 생산의 효율성과 개별 제품의 맞춤화(Customization)를 동시에 실현하는 재사용 체계
## 키워드
* 재사용, 도메인 공학, 애플리케이션 공학, 핵심 자산, 가변성
## 암기법
* 핵제관(핵심 자산, 제품 개발, 관리)
## 목적
- CBD 연장선상의 도메인 공학 개념
- 핵심자산 재사용으로 원가 경쟁력 확보
## 구성요소
- 핵심 자산 개발(Core Asset Development): 공통적으로 사용되는 컴포넌트, 아키텍처, 문서 개발 (Domain Engineering)
- 제품 개발(Product Development): 핵심 자산을 조합하고 개별 요구사항을 반영하여 제품 완성 (Application Engineering)
- 관리(Management): 조직적, 기술적 관점에서 전체 프로세스를 조율하고 운영
## 구성도 요소
* 아키텍처: Domain Engineering(자산 확보) <-> Application Engineering(제품 생산)
* 관계: 단순 코드 재사용을 넘어 분석, 설계, 테스트 등 전 단계의 자산 재사용 지향
```
[Domain Engineering] ---- (Core Assets) ----> [Application Engineering]
         |                                             |
   (Requirements)                              (Specific Product)
         |                                             |
         +------------- [Management] ------------------+
```
## 연관 토픽
- [[MVP]] - 제품 개발
