# REST API (Representational State Transfer API)

REST API는 HTTP 프로토콜 기반의 웹 서비스 아키텍처 스타일로, 클라이언트와 서버 간 상호작용을 단순하고 확장 가능하게 만듦. 자원의 상태를 표현하고 전송하는 방식을 의미함.

## 주요 특징

- **무상태성**: 각 요청은 독립적, 서버는 이전 요청 상태 미저장
- **클라이언트-서버 구조**: 클라이언트와 서버 독립적 동작
- **캐시 가능**: 응답의 캐시 가능성으로 성능 향상
- **계층화**: 아키텍처의 계층화 가능, 각 계층 독립 동작
- **인터페이스 일관성**: 일관된 인터페이스로 상호작용 단순화
- **코드 온디맨드 (선택적)**: 서버가 실행 가능 코드 전송 가능

## 구성 요소

- **자원 (Resource)**: URI로 식별되는 데이터 요소 (예: `/users`, `/posts`)
- **표현 (Representation)**: 자원 상태 나타내는 데이터 형식 (예: JSON, XML)
- **HTTP 메서드**: 자원에 대한 작업 정의 (예: GET, POST, PUT, DELETE)
- **HTTP 상태 코드**: 요청 결과 표시 (예: 200 OK, 404 Not Found)

## HTTP 메서드와 CRUD 연산

- GET: 자원 조회 (READ)
- POST: 새 자원 생성 (CREATE)
- PUT: 기존 자원 업데이트 (UPDATE)
- DELETE: 자원 삭제 (DELETE)
- PATCH: 자원 일부 업데이트 (PARTIAL UPDATE)

## API 예시 (사용자 관리)

### 1. 사용자 목록 조회 (GET /users)

요청:

```http
GET /users HTTP/1.1
Host: api.example.com
Accept: application/json
```

응답:

```http
HTTP/1.1 200 OK
Content-Type: application/json

[
  {"id": 1, "name": "Alice", "email": "alice@example.com"},
  {"id": 2, "name": "Bob", "email": "bob@example.com"}
]
```

### 2. 새 사용자 생성 (POST /users)

요청:

```http
POST /users HTTP/1.1
Host: api.example.com
Content-Type: application/json

{"name": "Charlie", "email": "charlie@example.com"}
```

응답:

```http
HTTP/1.1 201 Created
Content-Type: application/json

{"id": 3, "name": "Charlie", "email": "charlie@example.com"}
```

### 3. 사용자 정보 조회 (GET /users/{id})

요청:

```http
GET /users/1 HTTP/1.1
Host: api.example.com
Accept: application/json
```

응답:

```http
HTTP/1.1 200 OK
Content-Type: application/json

{"id": 1, "name": "Alice", "email": "alice@example.com"}
```

### 4. 사용자 정보 업데이트 (PUT /users/{id})

요청:

```http
PUT /users/1 HTTP/1.1
Host: api.example.com
Content-Type: application/json

{"name": "Alice Smith", "email": "alice.smith@example.com"}
```

응답:

```http
HTTP/1.1 200 OK
Content-Type: application/json

{"id": 1, "name": "Alice Smith", "email": "alice.smith@example.com"}
```

### 5. 사용자 삭제 (DELETE /users/{id})

요청:

```http
DELETE /users/1 HTTP/1.1
Host: api.example.com
```

응답:

```http
HTTP/1.1 204 No Content
```

## 주요 HTTP 상태 코드

- 200 OK: 요청 성공 처리
- 201 Created: 새 자원 생성 성공
- 204 No Content: 요청 성공 처리, 응답 본문 없음
- 400 Bad Request: 잘못된 요청
- 401 Unauthorized: 인증 필요
- 403 Forbidden: 접근 권한 없음
- 404 Not Found: 자원 미발견
- 500 Internal Server Error: 서버 내부 오류

## 설계 원칙

- **일관된 인터페이스**: 직관적이고 예측 가능한 API 설계
- **명확한 URI 구조**: 리소스 명확 식별 가능한 URI 사용
- **적절한 HTTP 메서드**: 각 작업에 맞는 HTTP 메서드 사용
- **유형화된 응답**: 일관된 데이터 형식 (예: JSON, XML) 사용
- **상태 코드 활용**: 적절한 HTTP 상태 코드로 결과 전달
- **보안 고려**: 인증 및 권한 부여로 API 보안 강화

REST API는 간단하고 확장 가능한 아키텍처 스타일로, 다양한 애플리케이션과 서비스 간 상호 운용성을 높임. 클라이언트-서버 간 효율적 데이터 전송과 상호작용을 가능케 함.
