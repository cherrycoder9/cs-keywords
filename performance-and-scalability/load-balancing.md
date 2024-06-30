# 로드 밸런싱 (Load Balancing)

로드 밸런싱은 네트워크 트래픽을 여러 서버로 분산시켜 시스템의 성능과 가용성을 향상시키는 기술. 단일 서버의 과부하를 방지하고 서비스의 안정성을 높이는 데 기여함.

## 주요 특징

- 트래픽 분산
- 고가용성 보장
- 시스템 확장성 제공
- 유연한 트래픽 분산 방식

## 유형

### 하드웨어 로드 밸런서

전용 장비를 통한 고성능, 고신뢰성 제공. 고비용.
예: F5 Networks, Cisco, Citrix NetScaler

### 소프트웨어 로드 밸런서

유연성과 비용 효율성이 높음.
예: Nginx, HAProxy, Apache HTTP Server

### 클라우드 로드 밸런서

간편한 설정, 자동 확장 기능 제공.
예: AWS ELB, Google Cloud Load Balancing, Azure Load Balancer

## 알고리즘

### 라운드 로빈

순차적으로 요청을 분산. 간단하고 균등한 분배 가능.

### 가중치 라운드 로빈

서버 성능에 따른 가중치 부여. 성능 차이 고려.

### IP 해시

클라이언트 IP 기반 서버 매핑. 세션 유지에 유용.

### 최소 연결

연결 수가 적은 서버로 요청 분배. 균등한 부하 분산.

### 최소 응답 시간

응답 시간이 짧은 서버로 요청 분배. 현재 서버 상태 고려.

## 설정 예시

### Nginx 로드 밸런싱

```nginx
http {
    upstream myapp {
        server server1.example.com;
        server server2.example.com;
        server server3.example.com;
    }
    server {
        listen 80;
        location / {
            proxy_pass http://myapp;
            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
            proxy_set_header X-Forwarded-Proto $scheme;
        }
    }
}
```

### AWS ELB 설정

1. AWS Management Console 로그인
2. EC2 Dashboard의 "Load Balancers" 선택
3. "Create Load Balancer" 클릭
4. 로드 밸런서 유형 선택
5. 로드 밸런서 설정 (이름, 리스너, 가용 영역 등)
6. 대상 그룹 설정
7. EC2 인스턴스 등록
8. 로드 밸런서 생성

## 장점

- 성능 향상
- 고가용성 확보
- 시스템 확장성 제공
- 유연한 트래픽 관리

## 사용 사례

- 웹 애플리케이션의 응답 속도 개선 및 가용성 유지
- 데이터베이스 읽기 요청 분산을 통한 성능 향상
- 파일 서버의 전송 속도 개선 및 가용성 유지
- 클라우드 환경에서의 자동 트래픽 분산

로드 밸런싱은 다양한 애플리케이션에서 성능과 가용성 향상을 위한 필수 기술. 효율적인 요청 처리와 안정적인 서비스 제공을 가능하게 함.
