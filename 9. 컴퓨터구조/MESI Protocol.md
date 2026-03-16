#컴퓨터구조 #캐시 #프로토콜 #필수 #컴퓨터구조/메모리
## 정의
캐시 라인 상태 기반 일관성 유지 프로토콜, MESI
- Modified, Exclusive, Shared, Invalid 4가지 상태로 캐시 일관성을 유지하는 스누핑 기반 프로토콜
## 키워드
* Modified, Exclusive, Shared, Invalid, Snooping, Write Hit, Write Miss, Read Hit, Read Miss
## 암기법
* "MESI" - Modified(수정), Exclusive(배타/유일), Shared(공유), Invalid(무효)
## 구성요소/특징/유형
| 상태 | 설명 | 비고 |
| ---- | ---- | ---- |
| M(Modified) | 캐시만 수정, 메인메모리와 불일치 | 쓰기 발생 |
| E(Exclusive) | 유일 캐시, 메인메모리와 동일 | 단독 소유 |
| S(Shared) | 2개 이상 캐시에 존재 | 읽기 공유 |
| I(Invalid) | 다른 캐시에서 수정됨, 무효 | 재로드 필요 |
## 연관 토픽
- [[Cache 일관성 유지 방법]] - 캐시 일관성 전체
- [[캐시 메모리]] - 캐시 기본 개념
