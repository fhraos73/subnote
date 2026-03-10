#정보관리기술사 #보안 #인증 #FIDO #WebAuthn #정리 #보안/인증/접근제어

## 정의
웹 표준 통합 비밀번호 없는 인증, FIDO 2.0
- FIDO Alliance와 W3C가 공동 개발한 웹 표준 기반의 비밀번호 없는 인증 기술
- WebAuthn(Web Authentication) API와 CTAP(Client to Authenticator Protocol)로 구성

## 키워드
* WebAuthn, CTAP, Passkey, 플랫폼 인증자, 로밍 인증자, W3C

## 암기법
* WebAuthn CTAP: (구성) WebAuthn(웹 API), CTAP(인증자 프로토콜)
* CTAP1 CTAP2: CTAP1(U2F 호환), CTAP2(확장 기능)

## 특징
- 웹 표준: W3C WebAuthn API 표준화
- 브라우저 내장: 별도 플러그인 불필요
- 플랫폼 통합: OS 내장 인증자 지원 (Windows Hello, Touch ID)
- Passkey: 클라우드 동기화 가능한 자격증명

## 목적
- 웹 환경에서 비밀번호 없는 인증 표준화
- 플랫폼/브라우저 간 호환성 확보
- 피싱 방지 및 사용자 편의성 향상

## 구성요소
| 구분 | 구성요소 | 설명 |
|------|----------|------|
| API | WebAuthn | 웹 브라우저 인증 API (W3C 표준) |
| 프로토콜 | CTAP1 | U2F 호환, 2차 인증 |
| 프로토콜 | CTAP2 | 비밀번호 없는 인증, PIN 지원 |
| 인증자 | 플랫폼 인증자 | 디바이스 내장 (Windows Hello, Touch ID) |
| 인증자 | 로밍 인증자 | 외부 보안키 (YubiKey 등) |
| 자격증명 | Passkey | 클라우드 동기화 가능한 FIDO 자격증명 |
| 서버 | Relying Party | 인증 요청/검증 서버 |

## 구성도
```
[FIDO 2.0 아키텍처]

[웹 애플리케이션] ◀──▶ [WebAuthn API] ◀──▶ [브라우저]
                                              │
                                         [CTAP]
                                              │
                              ┌───────────────┼───────────────┐
                              ▼               ▼               ▼
                        [플랫폼 인증자]  [로밍 인증자]   [Passkey]
                        (Windows Hello)  (YubiKey)     (클라우드 동기화)
                        (Touch ID)       (보안키)

[FIDO 1.0 vs FIDO 2.0]
┌─────────────────┬─────────────────┐
│    FIDO 1.0     │    FIDO 2.0     │
├─────────────────┼─────────────────┤
│ UAF + U2F       │ WebAuthn + CTAP │
│ 앱/브라우저 별도 │ 웹 표준 통합    │
│ 플러그인 필요   │ 브라우저 내장   │
│ 디바이스 종속   │ Passkey 동기화  │
└─────────────────┴─────────────────┘
```

## 연관 토픽
- [[FIDO 1.0]] - FIDO 1.0 UAF/U2F
- [[Passkey]] - 클라우드 동기화 자격증명
- [[생체인증]] - 지문, 안면 인증
- [[제로 트러스트]] - 지속적 인증
