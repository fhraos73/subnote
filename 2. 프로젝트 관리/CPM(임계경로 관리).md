#프로젝트관리 #일정관리 #필수

## 정의
프로젝트 일정 관리 CPM 정의
- 시간과 비용을 고려하여 프로젝트 일정을 관리하는 PDM(Procedure Diagram Method) 기법
- PDM 4가지 의존 관계 : FS, FF, SS, SF
	-  Finish to start, Finish to Finish, Start to Start, Start to finish
## 키워드
* Critical Path, Float(여유), 전진/후진 계산, PDM, 일정 단축 대상
## 암기법
* 전후여주 (전진계산, 후진계산, 여유시간, 주공정)
## 목적
- 프로젝트 완료를 위한 핵심 경로(Critical Path)를 파악
- 각 활동의 여유 시간(Float)을 계산하여 자원 배분의 우선순위를 결정하고 효율적인 일정 관리 지원
- 일정 지연 위험이 높은 작업을 집중 관리하여 프로젝트 지연을 예방하고 일정 단축 기법 적용의 근거 마련
## 구성요소
- 주경로(Critical Path): 여유 시간이 0인 가장 긴 경로 (프로젝트 최소 소요 시간 결정)
- 여유 시간(Float/Slack): 전체 여유(Total Float)와 자유 여유(Free Float)
- 전진 계산(Forward Pass): 활동의 조기 시작일(ES)과 조기 종료일(EF) 산정
- 후진 계산(Backward Pass): 활동의 늦은 시작일(LS)과 늦은 종료일(LF) 산정
- PDM(Precedence Diagramming Method): 선후 관계를 표현하는 네트워크 도식화법
## 구성도 요소
* 계산 공식:
    - EF = ES + Duration
    - LS = LF - Duration
    - Float = LS - ES 또는 LF - EF
* 관계: 임계 경로가 여러 개일 경우 프로젝트 위험도가 높아짐
```
[A: 3d] -- [B: 5d] -- [C: 2d]  => Path 1: 10d (Critical)
      \              /
       -- [D: 4d] ---          => Path 2: 7d (Float: 3d)
```
## 모범답안
- [모범답안](https://cafe.naver.com/f-e/cafes/12409209/articles/230219?menuid=892&referrerAllArticles=false&inCafeSearch=true&query=cpm&art=aW50ZXJuYWwtY2FmZS1hcnRpY2xlLXJlYWQtaW5DYWZlLXNlYXJjaC1saXN0.eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJjYWZlVHlwZSI6IkNBRkVfSUQiLCJhcnRpY2xlSWQiOjIzMDIxOSwiaXNzdWVkQXQiOjE3Njg4Mjg1MjMyMzIsImNhZmVJZCI6MTI0MDkyMDl9.70sdrwyJzYCJz5Ltawxixu8-WnEotZ2P6bdl3qjHZLE&page=1)
## 연관 토픽
- [[프로젝트 일정 관리(시간관리)]] - 일정 관리
- [[프로젝트 일정 단축기법]] - 일정 단축
## 임계 경로 도출 절차
- 정의 : 액티비티 정의 > 전후관계배열
- 계산 : 전진계산, 후진계산, 여유시간 계산
- 분석 : 임계 경로 분석, 수행시간 산정
- 프로젝트 임계경로 기간 도출
