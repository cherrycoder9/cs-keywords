# Web development

## [HTTP (Hypertext Transfer Protocol)](https://github.com/cherrycoder9/cs-keywords/blob/main/web-development/http.md)

- 웹 브라우저와 웹 서버 간 통신을 위한 프로토콜.
- 클라이언트의 요청(Request)과 서버의 응답(Response)으로 이루어짐.
- 상태 정보 유지 않는 Stateless 프로토콜임.

## [HTTPS (HTTP Secure)](https://github.com/cherrycoder9/cs-keywords/blob/main/web-development/https.md)

- HTTP에 SSL/TLS 암호화를 적용한 보안 프로토콜.
- 전송 데이터를 암호화하여 기밀성 보장함.
- 서버 인증서로 통신 상대방 신원 확인함.

## [REST API (Representational State Transfer API)](https://github.com/cherrycoder9/cs-keywords/blob/main/web-development/rest-api.md)

- 분산 시스템을 위한 아키텍처 스타일.
- 자원을 고유한 URI로 식별하고 HTTP 메서드로 자원에 대한 행위 정의함.
- 상태 정보 없이 요청 단위로 통신함.

## [웹소켓 (WebSocket)](https://github.com/cherrycoder9/cs-keywords/blob/main/web-development/websocket.md)

- 양방향 통신을 위한 프로토콜.
- HTTP 핸드셰이크 후 TCP 연결로 전환함.
- 실시간성이 중요한 애플리케이션에 사용됨.
- 서버 푸시 기능 제공.

## [인증 (Authentication)](https://github.com/cherrycoder9/cs-keywords/blob/main/web-development/authentication.md)

- 사용자 신원을 확인하는 과정.
- 아이디/비밀번호, 공개키 인증서 등 사용자 고유 정보 검증함.
- 보안 시스템의 기본 요소임.

## [인가 (Authorization)](https://github.com/cherrycoder9/cs-keywords/blob/main/web-development/authorization.md)

- 인증된 사용자의 권한을 확인하고 허용하는 과정.
- 접근 제어 목록, 역할 기반 접근 제어 등 방식 사용함.
- 중요 자원 보호에 필수적임.

## CORS (Cross-Origin Resource Sharing)

- 출처가 다른 자원 공유를 제어하는 정책.
- 교차 출처 요청에 대해 서버가 허용 여부 결정함.
- 브라우저의 동일 출처 정책 완화 목적.

## CSRF (Cross-Site Request Forgery)

- 사용자 의도와 무관한 위조 요청을 통한 공격.
- 인증된 사용자의 권한 악용함.
- 방지 위해 암호화된 토큰 사용해 요청 출처 검증함.

## XSS (Cross-Site Scripting)

- 악성 스크립트를 웹 페이지에 삽입하여 사용자 정보 탈취, 권한 탈취 등을 시도하는 공격.
- 입력 값 검증 및 출력 인코딩으로 방어.

## SQL 인젝션 (SQL Injection)

- 악의적인 SQL 문을 삽입하여 데이터베이스를 조작하는 공격.
- 매개변수화된 쿼리와 입력 값 검증으로 예방.

## SSL/TLS (Secure Sockets Layer/Transport Layer Security)

- 클라이언트-서버 간 암호화 통신을 제공하는 보안 프로토콜.
- 중요 정보 전송 시 필수적.

## 웹 서버 (Web Server)

- 클라이언트 요청에 따라 웹 리소스를 제공하는 소프트웨어.
- 대표적으로 Apache와 Nginx가 널리 사용됨.

## 웹 브라우저 (Web Browser)

- 웹 리소스를 요청하고 렌더링하는 클라이언트 애플리케이션.
- 사용자와 웹 서버 간 상호작용의 창구 역할.

## 프론트엔드 (Front-end)

- 사용자가 직접 보고 상호작용하는 웹 페이지 부분을 개발.
- UI/UX 디자인과 사용자 경험 향상에 주력.

## 백엔드 (Back-end)

- 웹 애플리케이션의 서버 측 로직과 데이터 처리를 담당.
- API 설계 및 데이터베이스 관리가 주요 업무.

## Canvas

- HTML5의 그래픽 요소.
- JavaScript로 동적 콘텐츠 생성 가능.
- 픽셀 단위 제어로 유연한 그래픽 처리 제공.

## WebGL (Web Graphics Library)

- 웹에서 3D 그래픽 렌더링을 위한 API.
- GPU 가속 활용해 고품질 3D 경험 구현.
- 게임, 시뮬레이션 등에 활용도 높음.

## OAuth (Open Authorization)

- 제3자 앱의 제한된 계정 접근을 허용하는 인증 프로토콜.
- 사용자가 권한 위임으로 개인정보 노출 최소화.
- 편리성과 보안성 향상.

## JWT (JSON Web Token)

- JSON 형식의 정보 전달 표준.
- 서명으로 무결성 입증.
- 사용자 인증, 정보 교환 시 효율적 활용.

## SPA (Single-Page Application)

- 단일 페이지 기반 웹앱.
- 동적 콘텐츠 갱신으로 사용자 경험 향상.
- 빠른 반응성과 개발 생산성 장점.

## MPA (Multi-Page Application)

- 다중 페이지 구조의 전통적 웹앱.
- 페이지 전환 시 서버 HTML 로드.
- 복잡한 구조에 적합하나 속도 저하 단점.

## SSR (Server-Side Rendering)

- 서버 측 페이지 렌더링 방식.
- 초기 로딩 속도 개선, SEO 최적화.
- 서버 부하 증가 고려 필요.

## CSR (Client-Side Rendering)

- 클라이언트 측 페이지 렌더링 방식.
- 동적 UI 구현 용이.
- 초기 로딩 지연, SEO 취약점 존재.

## DOM (Document Object Model)

- 문서를 논리 트리 구조로 표현한 객체 모델.
- 요소, 속성, 이벤트 등을 노드로 취급함.
- 문서 내용 동적 변경에 유용함.

## AJAX (Asynchronous JavaScript and XML)

- 비동기 방식으로 서버와 통신하는 기술.
- 페이지 전체 갱신 없이 일부만 업데이트함.
- 대화형 웹 애플리케이션 구현의 핵심.

## JSON (JavaScript Object Notation)

- 속성-값 쌍으로 이루어진 텍스트 기반 데이터 교환 형식.
- 간결하고 범용적임.
- 서버-클라이언트 간 데이터 전송에 널리 쓰임.

## XML (Extensible Markup Language)

- 데이터 구조를 기술하는 마크업 언어.
- 사용자 정의 태그로 계층적 데이터 표현.
- 데이터 저장과 교환에 활용.

## 쿠키 (Cookie)

- 웹 서버가 클라이언트에 저장하는 키-값 데이터.
- 사용자 식별, 개인화된 서비스 제공 등에 쓰임.
- 보안과 프라이버시 이슈 존재.

## 세션 (Session)

- 서버가 특정 클라이언트와 유지하는 지속적 연결 상태.
- 사용자별 데이터 관리에 이용됨.
- 인증, 장바구니 등 구현 시 필수.

## 라우팅 (Routing)

- 요청 URL을 해석해 적절한 처리 로직에 매핑하는 작업.
- 체계적인 URL 설계와 유지보수성 있는 코드 작성에 중요함.

## GraphQL

- 클라이언트가 필요한 데이터를 유연하게 요청하는 쿼리 언어.
- 단일 엔드포인트로 다양한 데이터 가져오기 가능.
- API 구현 단순화에 기여함.
