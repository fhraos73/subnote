#정보관리기술사 #디지털서비스 #XR #AR #VR #MR #정리

## 정의
확장현실 기술 통합 유형, XR
- VR(가상현실), AR(증강현실), MR(혼합현실), AV(증강가상) 등 현실과 가상을 융합하는 몰입형 기술의 총칭
- eXtended Reality, 현실-가상 연속체(Reality-Virtuality Continuum) 상의 모든 몰입형 경험 기술
## 키워드
* VR, AR, MR, AV, XR, HMD, DoF, Tracking, Registration, 정합기술, VRML, NUI
## 암기법
* 현실-가상 연속체: AR → AV → MR → VR (현실에서 가상으로)
* AR 핵심: 트레마인3 (Tracking, Registration, 마커인식, Interaction, 3D Processing)
## 특징
- 몰입감: 시각·청각·촉각 등 다중 감각 기반 몰입 경험 제공
- 현실-가상 융합: 현실 위에 가상 정보 오버레이 또는 완전 가상 공간 구현
- 실시간 상호작용: 사용자 동작·위치를 실시간 추적하여 반응
- 자유도 확장: 3-DoF(회전만) → 6-DoF(회전+이동) 자유도 진화
## 목적
- 물리적 한계를 초월한 몰입형 경험 제공(교육, 훈련, 엔터테인먼트)
- 산업 현장의 원격 협업 및 시뮬레이션 기반 의사결정 지원
## 구성요소
| 구분 | 유형 | 설명 |
|------|------|------|
| AR | 증강현실 | 현실 위에 가상 정보 오버레이 |
| AV | 증강가상 | 가상 세계에 현실 요소 결합 |
| MR | 혼합현실 | 현실과 가상이 실시간 상호작용 |
| VR | 가상현실 | 컴퓨터로 만든 완전 가상 공간 몰입 |
| XR | 확장현실 | AR+AV+MR+VR 전체를 아우르는 통칭 |
| AR 기술 | Tracking | 물체 움직임, 회전정보 추적 |
| AR 기술 | Registration | 정합기술(정적오차→렌더링오차→동적오차) |
| AR 기술 | 마커인식기술 | AR 마커 기반 객체 인식 |
| AR 기술 | Interaction | 2D/3D 시각 I/F, HMD |
| AR 기술 | 3D Processing | VRML, 3D 물리엔진 |
| VR 자유도 | 3-DoF | 고정 위치에서 머리 회전만(Yaw, Pitch, Roll) |
| VR 자유도 | 6-DoF | 공간이동 + 머리 방향 3축 |
## 구성도
```
[Reality-Virtuality Continuum]

 현실(Real) ◀─────────────────────────────▶ 가상(Virtual)
       │         │           │          │
      [AR]      [AV]        [MR]       [VR]
   증강현실   증강가상     혼합현실    가상현실
       └─────────┴───────────┴──────────┘
                      [XR: 확장현실]

[AR 구성기술] 트레마인3
  Tracking ── Registration ── 마커인식 ── Interaction ── 3D Processing

[정합기술 오차] 정적오차 → 렌더링오차 → 동적오차

[VR 자유도]
  3-DoF: Yaw(좌우) + Pitch(상하) + Roll(기울임) ← 고정 위치
  6-DoF: 3-DoF + X축(좌우이동) + Y축(상하이동) + Z축(전후이동)
```
## 연관 토픽
- [[메타버스]] - XR 기반 가상 세계
- [[공간 컴퓨팅]] - 공간 인식 기반 컴퓨팅
- [[NFT]] - 가상 자산 소유권
- [[디지털 트윈(Digital Twin)]] - 가상 모델링 기술
