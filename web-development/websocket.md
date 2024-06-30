# 웹소켓 (WebSocket)

웹소켓은 웹 브라우저와 서버 간 양방향 통신을 지원하는 프로토콜. HTTP와 달리 지속적 연결을 유지하며 실시간 데이터 교환이 가능함.

## 주요 특징

- **양방향 통신**: 클라이언트-서버 간 실시간 데이터 교환
- **지속적 연결**: 초기 연결 후 계속 유지
- **낮은 오버헤드**: HTTP 폴링 대비 네트워크 부하 감소
- **표준화**: IETF 표준 프로토콜, 대부분의 현대 웹 환경 지원

## 작동 원리

1. **핸드셰이크**: HTTP 요청으로 웹소켓 연결 요청, 서버 승인 시 WebSocket으로 프로토콜 전환
2. **데이터 전송**: 양방향 데이터 교환
3. **연결 유지**: 명시적 종료 요청 전까지 연결 유지

### 핸드셰이크 예시

클라이언트 요청:

```http
GET /chat HTTP/1.1
Host: example.com
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Key: dGhlIHNhbXBsZSBub25jZQ==
Sec-WebSocket-Version: 13
```

서버 응답:

```http
HTTP/1.1 101 Switching Protocols
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Accept: s3pPLMBiTxaQ9kYGzzhZRbK+xOo=
```

## 사용 이유

- **실시간 애플리케이션**: 채팅, 알림, 온라인 게임 등에 적합
- **효율적 통신**: 지속 연결로 불필요한 헤더 정보 반복 전송 방지
- **간단한 API**: 웹 브라우저와 서버에서 쉽게 구현 가능

## 구현 예시

### 클라이언트 (JavaScript)

```javascript
const socket = new WebSocket('ws://example.com/socket');

socket.onopen = (event) => {
    console.log('WebSocket connected');
    socket.send('Hello Server!');
};

socket.onmessage = (event) => {
    console.log('Received:', event.data);
};

socket.onerror = (event) => {
    console.error('WebSocket error:', event);
};

socket.onclose = (event) => {
    console.log('WebSocket closed');
};
```

### 서버 (Node.js, ws 라이브러리)

```javascript
const WebSocket = require('ws');
const wss = new WebSocket.Server({ port: 8080 });

wss.on('connection', (socket) => {
    console.log('Client connected');

    socket.on('message', (message) => {
        console.log('Received:', message);
        socket.send('Hello Client!');
    });

    socket.on('close', () => {
        console.log('Client disconnected');
    });
});
```

## 장점

- **실시간 통신**: 즉각적 데이터 교환
- **효율성**: 네트워크 오버헤드 감소
- **다양한 활용**: 채팅, 알림, 주식 시세, 온라인 게임 등

## 단점

- **복잡성**: 지속적 연결 관리와 오류 처리 필요
- **방화벽 문제**: 일부 네트워크에서 차단 가능성
- **리소스 소비**: 서버의 지속적 연결 유지에 추가 리소스 필요

## 활용 사례

- **채팅 앱**: 실시간 메시지 전송
- **알림 시스템**: 이메일, SNS 실시간 알림
- **온라인 게임**: 실시간 게임 상태/이벤트 업데이트
- **금융 앱**: 실시간 주식 시세/거래 정보
- **협업 도구**: 문서 편집, 프로젝트 관리 실시간 업데이트

웹소켓은 실시간 데이터 전송이 필요한 다양한 애플리케이션의 핵심 기술. 사용자 경험 향상과 효율적 통신을 실현함.
