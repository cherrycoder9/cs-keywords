# NoSQL

NoSQL(Not Only SQL)은 전통적인 관계형 데이터베이스 관리 시스템(RDBMS)과는 다른 접근 방식을 사용하는 데이터베이스 시스템임. 주로 비구조화된 대용량 데이터를 처리하기 위해 설계되었으며, 유연한 스키마와 높은 확장성을 특징으로 함.

## NoSQL의 주요 특징

1. **유연한 스키마**: 고정된 테이블 구조 없이 데이터를 저장할 수 있음.
2. **수평적 확장성**: 데이터베이스를 여러 서버에 분산하여 쉽게 확장할 수 있음.
3. **고성능**: 대량의 데이터를 빠르게 읽고 쓸 수 있음.
4. **다양한 데이터 모델**: 키-값, 문서, 컬럼 기반, 그래프 등 다양한 데이터 모델을 지원함.

## NoSQL 데이터베이스의 유형

### 1. 키-값 저장소

단순한 키-값 쌍으로 데이터를 저장함. 높은 성능과 확장성을 제공함.

- 예시: Redis, Amazon DynamoDB

```python
import redis

# Redis 연결
r = redis.Redis(host='localhost', port=6379, db=0)

# 데이터 저장
r.set('user:1', 'John Doe')

# 데이터 조회
print(r.get('user:1'))  # 출력: b'John Doe'
```

### 2. 문서 저장소

JSON과 유사한 형식의 문서로 데이터를 저장함. 복잡한 계층 구조를 표현할 수 있음.

- 예시: MongoDB, CouchDB

```javascript
// MongoDB 예시
db.users.insertOne({
    name: "John Doe",
    age: 30,
    email: "john@example.com",
    interests: ["programming", "music"]
});

// 데이터 조회
db.users.find({ name: "John Doe" });
```

### 3. 컬럼 기반 저장소

데이터를 컬럼 단위로 저장함. 대량의 데이터를 효율적으로 처리할 수 있음.

- 예시: Apache Cassandra, HBase

```sql
-- Cassandra CQL 예시
CREATE TABLE users (
    id UUID PRIMARY KEY,
    name TEXT,
    age INT,
    email TEXT
);

INSERT INTO users (id, name, age, email)
VALUES (uuid(), 'John Doe', 30, 'john@example.com');
```

### 4. 그래프 데이터베이스

노드와 엣지를 사용하여 데이터 간의 관계를 저장함. 복잡한 관계를 효율적으로 표현하고 탐색할 수 있음.

- 예시: Neo4j, Amazon Neptune

```cypher
// Neo4j Cypher 예시
CREATE (john:Person {name: 'John Doe', age: 30})
CREATE (jane:Person {name: 'Jane Doe', age: 28})
CREATE (john)-[:FRIEND_OF]->(jane)

// 관계 조회
MATCH (p:Person)-[:FRIEND_OF]->(friend)
RETURN p.name, friend.name
```

## NoSQL vs SQL

| 특성 | NoSQL | SQL |
|------|-------|-----|
| 스키마 | 유연함 | 고정됨 |
| 확장성 | 수평적 확장 용이 | 수직적 확장 위주 |
| 데이터 모델 | 다양함 (키-값, 문서, 컬럼, 그래프 등) | 테이블 기반 |
| 트랜잭션 | 제한적 지원 | ACID 트랜잭션 지원 |
| 쿼리 언어 | 데이터베이스별 다양한 API | 표준화된 SQL |
| 일관성 | 일반적으로 결과적 일관성 | 강한 일관성 |

## NoSQL의 장단점

### 장점

1. 대용량 데이터 처리에 적합
2. 높은 확장성과 성능
3. 유연한 데이터 모델링
4. 빠른 개발과 반복 가능

### 단점

1. 데이터 일관성 보장이 어려울 수 있음
2. 복잡한 조인 연산의 어려움
3. 표준화된 인터페이스 부족
4. 일부 기능에서 SQL 대비 성능 저하 가능

## NoSQL 사용 사례

1. **소셜 미디어 플랫폼**: 사용자 프로필, 포스트, 관계 등의 데이터 저장
2. **실시간 빅데이터 분석**: 로그 데이터, 센서 데이터 등의 대량 데이터 처리
3. **콘텐츠 관리 시스템**: 다양한 형식의 콘텐츠 저장 및 관리
4. **IoT 애플리케이션**: 센서 데이터의 실시간 수집 및 분석
5. **게임**: 사용자 프로필, 게임 상태, 리더보드 등의 데이터 관리

NoSQL 데이터베이스는 대규모 분산 시스템과 실시간 웹 애플리케이션에서 널리 사용됨. 특히 빠른 개발 주기, 대용량 데이터 처리, 유연한 데이터 모델이 요구되는 환경에서 강점을 보임. 그러나 데이터의 일관성과 복잡한 관계를 다루는 데에는 전통적인 관계형 데이터베이스가 여전히 적합한 경우가 많음. 따라서 프로젝트의 요구사항을 잘 파악하여 적절한 데이터베이스 시스템을 선택하는 것이 중요함.
