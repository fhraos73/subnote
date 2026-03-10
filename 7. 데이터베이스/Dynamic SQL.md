#데이터베이스 #SQL #프로그래밍 #필수 #데이터베이스/성능/튜닝
## 정의
실행 시점에 생성되는 SQL, Dynamic SQL
- 프로그램 실행 시점에 SQL 문장을 동적으로 생성하고 실행하는 기법
- 조건에 따라 다양한 쿼리를 유연하게 구성할 수 있으나 보안 주의 필요
## 키워드
* EXECUTE IMMEDIATE, PREPARE, 바인드 변수, SQL Injection, 파싱
## 암기법
* "동정비" - 동적 생성, 정적 대비, 비교
## Dynamic vs Static SQL
| 구분 | Dynamic SQL | Static SQL |
|------|-------------|------------|
| 생성 시점 | 실행 시점 | 컴파일 시점 |
| 유연성 | 높음 | 낮음 |
| 성능 | 상대적 낮음 | 높음 |
| 보안 | 취약 (주의 필요) | 안전 |
| 파싱 | 매번 파싱 | 1회 파싱 |
## 구현 방식
```sql
-- 방식 1: EXECUTE IMMEDIATE
EXECUTE IMMEDIATE 'SELECT * FROM ' || v_table;

-- 방식 2: PREPARE/EXECUTE
PREPARE stmt FROM 'SELECT * FROM emp WHERE id = ?';
EXECUTE stmt USING @emp_id;

-- 방식 3: 바인드 변수 (권장)
EXECUTE IMMEDIATE 'SELECT * FROM emp WHERE id = :1' USING v_id;
```
## 구성도
```
┌─────────────────────────────────────────┐
│           Dynamic SQL 처리 과정          │
├─────────────────────────────────────────┤
│ [SQL 문자열 생성] → [파싱] → [실행]      │
│  조건별 조합       구문분석   결과반환    │
├─────────────────────────────────────────┤
│ ⚠️ SQL Injection 방지: 바인드 변수 사용  │
└─────────────────────────────────────────┘
```
## SQL Injection 방지
| 취약 코드 | 안전 코드 |
|-----------|-----------|
| `'...WHERE id=' + input` | `'...WHERE id=:1' USING input` |
| 문자열 연결 | 바인드 변수 |
| 입력값 직접 삽입 | 파라미터화 쿼리 |
## 연관 토픽
- [[SQL Injection]] - 보안 취약점
- [[옵티마이저]] - 실행 계획
- [[DB 튜닝]] - 성능 최적화
