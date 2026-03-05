#SW공학 #오픈소스 #라이선스

## 정의
오픈소스 사용 조건 분류, 오픈소스 라이선스
- 오픈소스 소프트웨어의 사용, 수정, 배포 조건을 정의한 법적 계약으로, 카피레프트 강도에 따라 분류
- 저작권자의 권리와 사용자의 자유를 균형있게 보호하는 법적 프레임워크
## 키워드
- GPL, LGPL, AGPL, MIT, BSD, Apache, MPL
- Copyleft, Permissive, 파생저작물
- 소스코드 공개, 상업적 이용, 특허권
- OSI, FSF, 라이선스 양립성
## 암기법
- 강한 라이선스: 지에이 (GPL-AGPL)
- 중간 라이선스: 엘엠이 (LGPL-MPL-EPL)
- 허용적 라이선스: 마바아 (MIT-BSD-Apache)
- 카피레프트: 수정하면 똑같이 공개해라
## 목적
- 오픈소스 사용 조건의 명확한 정의 및 법적 보호
- 저작권자 권리와 사용자 자유의 균형 유지
## 구성요소
### Copyleft(카피레프트) - 강한 라이선스
- GPL(General Public License): 파생저작물도 GPL로 공개 의무
- AGPL(Affero GPL): 네트워크 서비스도 소스 공개 의무
- 특징: 소스코드 공개 의무, 동일 라이선스 적용
### Weak Copyleft(약한 카피레프트) - 중간 라이선스
- LGPL(Lesser GPL): 라이브러리 링크 시 독점 SW 허용
- MPL(Mozilla Public License): 파일 단위 카피레프트
- EPL(Eclipse Public License): 모듈 단위 카피레프트
- 특징: 부분적 소스 공개, 독점 SW와 결합 가능
### Permissive(허용적) - 약한 라이선스
- MIT License: 최소 제약, 상업적 이용 자유
- BSD License: MIT와 유사, 3-Clause/2-Clause 버전
- Apache License 2.0: 특허권 보호 조항 포함
- 특징: 소스 공개 의무 없음, 재배포 시 라이선스 표시만 필요
## 구성도
```
[라이선스 스펙트럼]

강한 제약 ◄──────────────────────► 약한 제약
(Copyleft)                      (Permissive)

  AGPL  GPL  LGPL  MPL  Apache  MIT  BSD
   │     │     │     │     │      │    │
   └─강한─┴─약한──────┴─────────허용적─┘
        Copyleft              Permissive

[주요 라이선스 비교]

                GPL   LGPL   MIT   Apache
소스공개의무     O      △     X      X
파생물라이선스   동일   부분   자유   자유
상업적이용      O      O     O      O
특허보호        X      X     X      O
재배포조건      엄격   중간   단순   중간

[선택 기준]

┌─────────────────────────────────────┐
│  공개 의무를 원하는가?               │
│         YES │ NO                    │
│             ▼                       │
│        GPL, AGPL                    │
│                                     │
│  라이브러리인가?                     │
│         YES │ NO                    │
│             ▼                       │
│           LGPL                      │
│                                     │
│  특허 보호가 필요한가?               │
│         YES │ NO                    │
│             ▼                       │
│         Apache    MIT/BSD           │
└─────────────────────────────────────┘
```
## 연관 토픽
- [[오픈소스 소프트웨어]] - 오픈소스 기본 개념
## 특징
- 법적 구속력: 법적 효력이 있는 계약
- 단계별 분류: 카피레프트 강도 구분
- 양립성: 라이선스 간 호환성 고려
- 명확성: 사용 조건 명시적 정의
## Close Source S/W License 폐쇄형 라이선스
- 사용자에게 특정 조건 하(클라우드 이용 고객사만 이용)에서만 저작물을 사용할 수 있는 권한을 부여
	- SSPL(ServiceSidePublicLicense) : 자사 서비스 이용 고객에게만 무료, MongoDB, Redis
	- BSL(Business Source License) : 상업적 불가, SW 공개
