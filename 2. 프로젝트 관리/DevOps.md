#프로젝트관리 #DevOps #필수

## 정의
개발과 운영의 협업을 통한 신속한 가치 전달 체계, 데브옵스
- ==Development(개발)와 Operations(운영)==의 합성어로, 문화, 방식, 도구의 통합을 의미함
- 소프트웨어 개발 생애주기(SDLC)를 단축하고 고품질의 서비스를 지속적으로 제공하는 것이 목표
## 키워드
* CAMS(Culture, Automation, Measurement, Sharing), CI/CD, IaC, 무한대 루프
## 암기법
* 캠스(CAMS), 계코빌테 배설운모 (계획, 코드, 빌드, 테스트, 배포, 설정, 운영, 모니터링)
## 구성요소
- 문화(Culture): 공유된 책임, 협업, 실패를 두려워하지 않는 문화
- 자동화(Automation): CI/CD 파이프라인, IaC(코드 기반 인프라), 자동 테스트
- 측정(Measurement): KPI 기반의 성과 측정 및 실시간 모니터링
- 공유(Sharing): 지식과 도구의 공유를 통한 피드백 루프 강화
- 지속적 개선: 릴리스 후 운영 데이터를 개발에 즉시 반영하는 환류 체계
## 구성도 요소
* 무한대 루프: Plan -> Code -> Build -> Test -> Release -> Deploy -> Operate -> Monitor -> (반복)
* 관계: Agile(방법론) + Lean(철학) + Automation(기술)의 결합체
```
 ( Plan ) <---------- ( Monitor )
    |                    ^
 ( Code )            ( Operate )
    |                    ^
 ( Build )           ( Deploy  )
    |                    ^
 ( Test  ) ---------> ( Release )
```
## 연관 토픽
- [[CI, CD]] - 지속적 통합/배포
- [[MSA와 Monolithic Architecture]] - MSA 아키텍처
- [[디지털 전환(DX)]] - 디지털 전환
- [[ITSM]] - IT 서비스 관리
- [[무중단 배포 기법]] - 배포 전략
