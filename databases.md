# Databases

## [데이터베이스 (Database)](https://github.com/cherrycoder9/cs-keywords/blob/main/databases/database.md)

- 구조화되고 조직화된 데이터의 집합.
- 효율적인 저장, 검색, 관리를 위해 설계됨.
- 응용 프로그램의 기반이 되는 정보 저장소.

## [관계형 데이터베이스 (RDBMS: Relational Database Management System)](https://github.com/cherrycoder9/cs-keywords/blob/main/databases/RDBMS.md)

- 데이터를 2차원 테이블로 표현하고 관리하는 데이터베이스.
- 테이블 간 관계 설정으로 데이터 일관성과 무결성 유지.
- 대표적으로 MySQL, Oracle 등.

## [SQL (Structured Query Language)](https://github.com/cherrycoder9/cs-keywords/blob/main/databases/SQL.md)

- 관계형 데이터베이스에서 데이터 정의, 조작, 제어를 위한 표준 질의어.
- 선언적 언어로서 데이터베이스 객체 생성, 수정, 삭제, 검색 등 수행.

## [NoSQL (Not Only SQL)](https://github.com/cherrycoder9/cs-keywords/blob/main/databases/NoSQL.md)

- 비정형, 반정형 데이터를 다루기 위한 유연한 데이터 모델 기반 데이터베이스.
- 수평적 확장성과 고성능 특징.
- 키-값, 문서, 컬럼, 그래프 등 다양한 유형 존재.

## 트랜잭션 (Transaction)

- 데이터베이스의 상태를 변화시키는 하나의 작업 단위.
- 성공 시 모두 반영, 실패 시 모두 취소되는 원자성 보장.
- 병행 수행 시 고립성 유지.

## 데이터 일관성 (Data Consistency)

- 데이터베이스의 모든 데이터가 정확하고 유효한 상태로 유지되는 것.
- 무결성 제약조건 준수, 트랜잭션 처리 등을 통해 달성.

## ACID

- 트랜잭션의 안전성을 보장하는 4가지 특성.
- 원자성(All-or-Nothing)
- 일관성(Data Integrity)
- 고립성(Concurrency Control)
- 지속성(Durability).

## BASE (Basically Available, Soft state, Eventually consistent)

- 가용성과 확장성 중시하는 분산 시스템 설계 원칙.
- 데이터 일관성보다 성능 우선시함.
- 최종적으로는 일관성 보장.

## 샤딩 (Sharding)

- 데이터를 여러 노드로 분할 저장하는 기법.
- 각 노드는 데이터 부분집합 담당함.
- 수평적 확장성과 성능 향상 목적.

## 복제 (Replication)

- 동일한 데이터를 여러 노드에 중복 저장.
- 가용성과 내결함성 향상시킴.
- 장애 발생 시 서비스 연속성 보장.

## 인덱스 (Index)

- 데이터 검색 성능 향상을 위한 자료구조.
- 키 값과 레코드 주소 쌍으로 구성됨.
- 추가 저장 공간 차지함.

## 스키마 (Schema)

- 데이터베이스 구조를 정의하는 메타데이터.
- 테이블, 컬럼, 제약조건 등 포함함.
- 데이터 일관성 유지에 필수적.

## 객체 관계 매핑 (Object-Relational Mapping)

- 객체지향 모델과 관계형 모델 간 불일치 해소하는 기술.
- 객체와 테이블 자동 매핑함.
- 생산성 증대시킴.

## 정규화 (Normalization)

- 데이터 중복과 이상 현상 제거 위한 과정.
- 함수적 종속성에 따라 테이블 분해함.
- 데이터 무결성 보장함.

## 기본 키 (Primary Key)

- 테이블에서 각 레코드를 고유하게 식별하는 속성.
- 중복과 Null 값 허용 않음.
- 테이블 당 하나만 지정 가능함.

## 외래 키 (Foreign Key)

- 다른 테이블의 기본 키를 참조하는 속성.
- 테이블 간 관계 설정에 사용.
- 참조 무결성 보장함.

## 조인 (Join)

- 두 개 이상의 테이블을 연관된 열을 기준으로 연결하는 연산.
- 테이블 간 데이터 통합 시 활용.
- 조인 조건 설정이 중요함.

## 뷰 (View)

- 기본 테이블에서 파생된 가상의 테이블.
- 특정 사용자에게 필요한 데이터만 제공.
- 실제 데이터 저장 않음.

## 저장 프로시저 (Stored Procedure)

- 일련의 SQL 문을 캡슐화한 데이터베이스 객체.
- 모듈화로 유지보수성 향상.
- 성능 및 보안성 개선에 기여함.

## 트리거 (Trigger)

- 테이블에 대한 특정 이벤트 발생 시 자동 실행되는 프로시저.
- DML 문에 대한 응답으로 작동.
- 데이터 무결성 유지에 효과적임.

## 데이터 모델링 (Data Modeling)

- 업무에 필요한 데이터를 식별하고 구조화하는 과정.
- 개념적, 논리적, 물리적 단계로 구성.
- 데이터베이스 설계의 핵심임.

## 데이터 마이닝 (Data Mining)

- 방대한 데이터에서 유용한 지식을 추출하는 기법.
- 통계, 기계학습 알고리즘 활용.
- 의사 결정 지원에 활용함.

## 데이터 웨어하우스 (Data Warehouse)

- 의사 결정 지원을 위한 통합된 데이터 저장소.
- 다양한 소스의 데이터 수집 및 정제.
- 대량 데이터 분석에 최적화됨.
