#정보관리기술사 #디지털서비스 #가상화 #Hypervisor #정리

## 정의
서버 자원 가상화 관리 소프트웨어, Hypervisor
- CPU, 메모리, 하드디스크 등 서버 자원들을 가상화 기술을 적용하여 효율적으로 관리하는 소프트웨어
- VMM(Virtual Machine Monitor)이라고도 하며, 가상 머신을 생성하고 실행하는 프로세스
## 키워드
* VMM, Type1(Native/Bare-metal), Type2(Hosted), 전가상화, 반가상화, Xen, KVM, VMware
## 암기법
* Type1: 하드웨어 위 직접(Native) / Type2: 호스트 OS 위(Hosted)
## 특징
- 자원 추상화: 물리적 하드웨어를 논리적 자원으로 추상화하여 VM에 할당
- 격리성: 각 VM은 독립적 환경으로 운영되어 상호 영향 최소화
- 하드웨어 독립성: 이기종 OS를 하나의 물리 서버에서 동시 운영 가능
- 오버헤드: 가상화 레이어로 인한 성능 저하 존재(컨테이너 대비)
## 구성요소
| 유형 | 구조 | 대표 기술 | 설명 |
|------|------|-----------|------|
| Type1 (Native/Bare-metal) | HW → Hypervisor → VM | Xen, KVM, VMware ESXi | 하드웨어 위에 직접 설치, 고성능 |
| Type2 (Hosted) | HW → Host OS → Hypervisor → VM | VMware Workstation, VirtualBox | 호스트 OS 위에 설치, 편의성 |
## 구성도
```
[Type1: Native/Bare-metal]        [Type2: Hosted 기반]

┌──────┐ ┌──────┐ ┌──────┐    ┌──────┐ ┌──────┐ ┌──────┐
│ VM 1 │ │ VM 2 │ │ VM 3 │    │ VM 1 │ │ VM 2 │ │ VM 3 │
│(OS A)│ │(OS B)│ │(OS C)│    │(OS A)│ │(OS B)│ │(OS C)│
├──────┴─┴──────┴─┴──────┤    ├──────┴─┴──────┴─┴──────┤
│     Hypervisor (VMM)    │    │     Hypervisor (VMM)    │
│    (Type1: Bare-metal)  │    │       (Type2: Hosted)   │
├─────────────────────────┤    ├─────────────────────────┤
│                         │    │       Host OS           │
│      Hardware           │    ├─────────────────────────┤
│                         │    │      Hardware           │
└─────────────────────────┘    └─────────────────────────┘
```
## 연관 토픽
- [[가상화]] - IT 인프라 가상화 전반
- [[도커(Docker)]] - 컨테이너 기반 가상화(OS 레벨)
- [[클라우드 네이티브]] - 클라우드 네이티브 아키텍처
