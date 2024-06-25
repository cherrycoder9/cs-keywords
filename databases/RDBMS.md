# 관계형 데이터베이스

관계형 데이터베이스(Relational Database)는 데이터를 테이블 형태로 구조화하고, 이들 테이블 간의 관계를 정의하여 데이터를 효율적으로 관리하는 데이터베이스 시스템임. SQL(Structured Query Language)을 사용하여 데이터를 조작하고 관리함.

## 주요 특징

1. **구조화된 데이터**: 데이터를 행(Row)과 열(Column)로 구성된 테이블(Table)에 저장함.
2. **데이터 무결성**: 제약 조건을 통해 데이터의 정확성과 일관성을 보장함.
3. **관계 정의**: 외래 키(Foreign Key)를 사용하여 테이블 간의 관계를 정의함.
4. **SQL 사용**: 표준화된 쿼리 언어를 사용하여 데이터를 조작함.
5. **ACID 트랜잭션**: 데이터의 일관성과 신뢰성을 보장하는 트랜잭션을 지원함.

## 주요 구성 요소

- **테이블 (Table)**: 데이터를 저장하는 기본 단위
- **행 (Row)**: 단일 데이터 레코드
- **열 (Column)**: 데이터의 속성
- **기본 키 (Primary Key)**: 각 행을 고유하게 식별하는 열
- **외래 키 (Foreign Key)**: 다른 테이블과의 관계를 정의하는 열

## SQL 주요 명령어

### 데이터 정의어 (DDL)

```sql
-- 테이블 생성
CREATE TABLE Employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(50),
    salary DECIMAL(10, 2)
);

-- 테이블 구조 변경
ALTER TABLE Employees ADD COLUMN hire_date DATE;

-- 테이블 삭제
DROP TABLE Employees;
```

### 데이터 조작어 (DML)

```sql
-- 데이터 삽입
INSERT INTO Employees (id, name, department, salary)
VALUES (1, '홍길동', 'IT', 50000.00);

-- 데이터 조회
SELECT * FROM Employees WHERE department = 'IT';

-- 데이터 수정
UPDATE Employees SET salary = 55000.00 WHERE id = 1;

-- 데이터 삭제
DELETE FROM Employees WHERE id = 1;
```

### 데이터 제어어 (DCL)

```sql
-- 권한 부여
GRANT SELECT, INSERT ON Employees TO 'user'@'localhost';

-- 권한 회수
REVOKE INSERT ON Employees FROM 'user'@'localhost';
```

### 트랜잭션 제어어 (TCL)

```sql
-- 트랜잭션 시작
START TRANSACTION;

-- 데이터 수정
UPDATE Employees SET salary = 60000.00 WHERE id = 1;

-- 트랜잭션 완료
COMMIT;

-- 트랜잭션 취소
ROLLBACK;
```

## 관계 모델링

### 1:1 관계

```sql
CREATE TABLE Person (
    id INT PRIMARY KEY,
    name VARCHAR(100)
);

CREATE TABLE Passport (
    id INT PRIMARY KEY,
    passport_number VARCHAR(20),
    person_id INT UNIQUE,
    FOREIGN KEY (person_id) REFERENCES Person(id)
);
```

### 1:N 관계

```sql
CREATE TABLE Department (
    id INT PRIMARY KEY,
    name VARCHAR(50)
);

CREATE TABLE Employee (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES Department(id)
);
```

### M:N 관계

```sql
CREATE TABLE Student (
    id INT PRIMARY KEY,
    name VARCHAR(100)
);

CREATE TABLE Course (
    id INT PRIMARY KEY,
    name VARCHAR(100)
);

CREATE TABLE Enrollment (
    student_id INT,
    course_id INT,
    PRIMARY KEY (student_id, course_id),
    FOREIGN KEY (student_id) REFERENCES Student(id),
    FOREIGN KEY (course_id) REFERENCES Course(id)
);
```

## 고급 기능

### 인덱싱

```sql
-- 인덱스 생성
CREATE INDEX idx_employee_name ON Employees(name);

-- 인덱스를 사용한 쿼리
SELECT * FROM Employees WHERE name = '홍길동';
```

### 뷰 (View)

```sql
-- 뷰 생성
CREATE VIEW HighSalaryEmployees AS
SELECT * FROM Employees WHERE salary > 50000;

-- 뷰 사용
SELECT * FROM HighSalaryEmployees;
```

### 저장 프로시저

```sql
DELIMITER //
CREATE PROCEDURE GiveRaise(IN employeeId INT, IN raiseAmount DECIMAL(10, 2))
BEGIN
    UPDATE Employees
    SET salary = salary + raiseAmount
    WHERE id = employeeId;
END //
DELIMITER ;

-- 프로시저 호출
CALL GiveRaise(1, 5000.00);
```

관계형 데이터베이스는 데이터의 일관성, 정확성, 보안성을 보장하면서도 복잡한 쿼리와 트랜잭션을 효율적으로 처리할 수 있어 기업 환경에서 널리 사용됨. 데이터의 구조화된 저장과 관리가 필요한 대부분의 애플리케이션에서 핵심적인 역할을 수행함.

효과적인 관계형 데이터베이스 설계를 위해서는 정규화, 인덱싱 전략, 트랜잭션 관리, 성능 최적화 등에 대한 깊은 이해가 필요함. 또한, 대규모 데이터 처리와 고가용성이 요구되는 환경에서는 데이터베이스 클러스터링, 복제, 샤딩 등의 고급 기술이 적용됨.
