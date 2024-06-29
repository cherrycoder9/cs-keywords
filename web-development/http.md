# HTTP (Hypertext Transfer Protocol)

HTTP는 월드 와이드 웹에서 하이퍼텍스트 문서를 전송하기 위한 응용 계층 프로토콜. 클라이언트와 서버 간 요청-응답 방식으로 동작하며, 인터넷 데이터 통신의 표준 규약.

## 주요 특징

- **비연결성**: 요청-응답 후 연결 종료
- **무상태성**: 각 요청은 독립적, 상태 정보 미저장
- **유연성**: 다양한 데이터 형식 전송 가능, 높은 확장성
- **계층 구조**: TCP/IP 스택의 상위 계층에서 동작

## HTTP 메서드

- **GET**: 리소스 요청 및 조회
- **POST**: 데이터 전송, 리소스 생성/업데이트
- **PUT**: 데이터 전송, 리소스 생성/대체
- **DELETE**: 리소스 삭제
- **HEAD**: 리소스 헤더 정보 요청
- **OPTIONS**: 서버 지원 HTTP 메서드 확인
- **PATCH**: 리소스 부분 업데이트

## HTTP 상태 코드

- **1xx (정보)**: 요청 수신, 처리 중
  - 100 Continue: 요청 일부 수신, 계속 진행
- **2xx (성공)**: 요청 성공적 처리
  - 200 OK: 요청 성공
  - 201 Created: 요청 성공, 새 리소스 생성
- **3xx (리다이렉션)**: 리소스 위치 변경
  - 301 Moved Permanently: 영구 이동
  - 302 Found: 임시 이동
- **4xx (클라이언트 오류)**: 클라이언트 요청 오류
  - 400 Bad Request: 잘못된 요청
  - 401 Unauthorized: 인증 필요
  - 403 Forbidden: 요청 거부
  - 404 Not Found: 리소스 없음
- **5xx (서버 오류)**: 서버 처리 중 오류 발생
  - 500 Internal Server Error: 서버 내부 오류
  - 502 Bad Gateway: 게이트웨이/프록시 오류
  - 503 Service Unavailable: 서비스 불가

## HTTP 헤더

- **요청 헤더**:
  - `Host`: 요청 서버 호스트명
  - `User-Agent`: 클라이언트 소프트웨어 정보
  - `Accept`: 수락 가능 콘텐츠 유형
  - `Authorization`: 인증 정보
- **응답 헤더**:
  - `Server`: 서버 소프트웨어 정보
  - `Content-Type`: 응답 콘텐츠 유형
  - `Set-Cookie`: 설정할 쿠키 정보
  - `Location`: 리다이렉션 URL

## 요청/응답 예시

### GET 요청

```http
GET /index.html HTTP/1.1
Host: www.example.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
```

### 응답

```http
HTTP/1.1 200 OK
Date: Mon, 27 Jul 2020 12:28:53 GMT
Server: Apache/2.4.1 (Unix)
Content-Type: text/html
Content-Length: 1024

<html>
<head>
    <title>Example Page</title>
</head>
<body>
    <h1>Hello, World!</h1>
</body>
</html>
```
