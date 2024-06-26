# SQL (Structured Query Language)

SQL은 관계형 데이터베이스 관리 시스템(RDBMS)에서 데이터를 관리하고 조작하기 위한 표준화된 프로그래밍 언어임. 데이터의 정의, 조작, 제어를 위한 포괄적인 기능을 제공함.

## SQL의 주요 구성 요소

1. **데이터 정의어 (DDL)**: 데이터베이스 구조를 정의
2. **데이터 조작어 (DML)**: 데이터를 조작
3. **데이터 제어어 (DCL)**: 데이터 접근 권한을 관리
4. **트랜잭션 제어어 (TCL)**: 트랜잭션을 관리

## 주요 SQL 명령어

### 데이터 정의어 (DDL)

```sql
-- 데이터베이스 생성
CREATE DATABASE school;

-- 테이블 생성
CREATE TABLE students (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50) NOT NULL,
    age INT,
    grade FLOAT
);

-- 테이블 구조 변경
ALTER TABLE students ADD COLUMN email VARCHAR(100);

-- 테이블 삭제
DROP TABLE students;
```

### 데이터 조작어 (DML)

```sql
-- 데이터 삽입
INSERT INTO students (name, age, grade) VALUES ('홍길동', 20, 3.5);

-- 데이터 조회
SELECT * FROM students WHERE age > 18;

-- 데이터 수정
UPDATE students SET grade = 4.0 WHERE name = '홍길동';

-- 데이터 삭제
DELETE FROM students WHERE id = 1;
```

### 데이터 제어어 (DCL)

```sql
-- 권한 부여
GRANT SELECT, INSERT ON students TO 'user'@'localhost';

-- 권한 회수
REVOKE INSERT ON students FROM 'user'@'localhost';
```

### 트랜잭션 제어어 (TCL)

```sql
-- 트랜잭션 시작
START TRANSACTION;

-- 데이터 조작 명령어들...

-- 트랜잭션 완료
COMMIT;

-- 트랜잭션 취소
ROLLBACK;
```

## 고급 SQL 기능

### JOIN

여러 테이블의 데이터를 결합하는 연산

```sql
-- INNER JOIN
SELECT students.name, courses.course_name
FROM students
INNER JOIN enrollments ON students.id = enrollments.student_id
INNER JOIN courses ON enrollments.course_id = courses.id;

-- LEFT JOIN
SELECT students.name, courses.course_name
FROM students
LEFT JOIN enrollments ON students.id = enrollments.student_id
LEFT JOIN courses ON enrollments.course_id = courses.id;
```

### 서브쿼리

쿼리 내에 중첩된 또 다른 쿼리

```sql
-- 서브쿼리 예시
SELECT name, grade
FROM students
WHERE grade > (SELECT AVG(grade) FROM students);
```

### 집계 함수

데이터의 집계 결과를 계산

```sql
SELECT 
    COUNT(*) as total_students,
    AVG(grade) as average_grade,
    MAX(grade) as highest_grade,
    MIN(grade) as lowest_grade
FROM students;
```

### 그룹화

데이터를 그룹으로 묶어 집계

```sql
SELECT age, AVG(grade) as average_grade
FROM students
GROUP BY age
HAVING AVG(grade) > 3.0;
```

### 뷰 (View)

가상 테이블을 생성하여 복잡한 쿼리를 단순화

```sql
CREATE VIEW high_performers AS
SELECT name, grade
FROM students
WHERE grade > 3.5;

SELECT * FROM high_performers;
```

### 인덱스 (Index)

데이터 검색 속도를 향상시키는 데이터 구조

```sql
CREATE INDEX idx_student_name ON students(name);
```

## SQL의 장점

1. **표준화**: 다양한 RDBMS에서 사용 가능한 표준 언어
2. **선언적 언어**: 원하는 결과를 명시하면 DBMS가 최적의 실행 계획을 수립
3. **높은 수준의 추상화**: 복잡한 데이터 조작을 간단한 명령으로 수행
4. **데이터 무결성 보장**: 제약 조건을 통해 데이터의 정확성과 일관성 유지
5. **트랜잭션 지원**: 데이터의 안정성과 일관성 보장

SQL은 데이터베이스 관리와 데이터 분석에 필수적인 도구로, 데이터 중심의 현대 애플리케이션 개발에 광범위하게 사용됨. 효과적인 SQL 사용을 위해서는 데이터베이스 설계 원칙, 쿼리 최적화 기법, 인덱싱 전략 등에 대한 깊은 이해가 필요함.

특히 대규모 데이터 처리와 복잡한 비즈니스 로직 구현에 있어 SQL의 고급 기능들(예: 윈도우 함수, CTE, 피벗 등)을 활용하면 더욱 효율적인 데이터 처리가 가능함. 또한, 각 RDBMS의 특정 기능과 최적화 기법을 숙지하면 더욱 향상된 성능을 얻을 수 있음.
