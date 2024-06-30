# HTTPS (HTTP Secure)

HTTPS는 HTTP에 보안 계층을 추가한 프로토콜로, 웹 브라우저와 서버 간 통신을 암호화하여 데이터의 기밀성과 무결성을 보장함. SSL(Secure Sockets Layer) 또는 TLS(Transport Layer Security) 프로토콜을 사용해 데이터를 암호화함.

## 주요 특징

- **암호화**: 클라이언트-서버 간 통신 내용 보호
- **인증**: 서버 신원 인증으로 신뢰성 보장
- **무결성**: 전송 중 데이터 변조 방지

## 작동 원리

### 1. SSL/TLS 핸드셰이크

- **클라이언트 헬로**: 지원 SSL/TLS 버전, 암호화 방법, 세션 ID 전송
- **서버 헬로**: 선택된 SSL/TLS 버전, 암호화 방법, 세션 ID 응답
- **서버 인증**: 서버 인증서(공개 키 포함) 전송
- **키 교환**: 공개 키 암호화로 대칭 키 생성 위한 키 교환
- **세션 생성**: 대칭 키로 세션 생성, 이후 통신 암호화

### 2. 데이터 전송

핸드셰이크 완료 후 모든 데이터 전송이 암호화됨

## 구성 요소

- **SSL/TLS 인증서**: 서버 신원 인증, 공개 키 포함 디지털 인증서
- **공개 키/개인 키**: 비대칭 암호화용 키 쌍
- **대칭 키**: 데이터 전송 시 사용하는 암호화 키

## 설정 예시 (Nginx)

### SSL/TLS 인증서 생성 (Let's Encrypt)

```sh
sudo apt-get install certbot python3-certbot-nginx
sudo certbot --nginx -d yourdomain.com -d www.yourdomain.com
```

### Nginx 설정

```nginx
server {
    listen 80;
    server_name yourdomain.com www.yourdomain.com;
    return 301 https://$host$request_uri;
}

server {
    listen 443 ssl;
    server_name yourdomain.com www.yourdomain.com;
    ssl_certificate /etc/letsencrypt/live/yourdomain.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/yourdomain.com/privkey.pem;
    ssl_protocols TLSv1.2 TLSv1.3;
    ssl_ciphers HIGH:!aNULL:!MD5;

    location / {
        proxy_pass http://localhost:5000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

## 장점

- **높은 보안성**: 중간자 공격 및 도청 방지
- **신뢰성 향상**: 서버 신원 인증으로 신뢰할 수 있는 통신 보장
- **SEO 개선**: 검색 엔진이 HTTPS 웹사이트를 우선시

## 단점

- **미미한 성능 저하**: 암호화/복호화로 인한 추가 연산
- **관리 복잡성**: SSL/TLS 인증서 관리 및 설정 필요
- **잠재적 비용**: 유료 인증서 사용 시 추가 비용 발생 가능

## 활용 사례

- **전자상거래**: 결제 정보 및 개인 정보 보호
- **온라인 서비스**: 로그인 정보와 사용자 데이터 보호
- **API 통신**: API 요청 및 응답 데이터 보호
- **일반 웹사이트**: 웹사이트 보안 및 신뢰성 향상

HTTPS는 현대 웹 보안의 필수 요소로, 모든 웹사이트에서의 사용이 권장됨. 사용자 데이터 보호와 웹사이트 신뢰성 향상에 기여함.
