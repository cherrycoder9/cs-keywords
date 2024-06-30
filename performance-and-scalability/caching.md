# 캐싱 (Caching)

캐싱은 자주 사용하는 데이터나 연산 결과를 일시적으로 저장하여 빠른 접근을 가능케 하는 기술. 성능 향상과 응답 시간 단축에 널리 활용됨.

## 주요 특징

- 빠른 접근이 가능한 저장소에 데이터 보관
- 원본 데이터 소스보다 신속한 데이터 접근
- 일정 기간 동안만 데이터 유지

## 목적

- 시스템 성능 향상
- 응답 시간 단축
- 자원 사용 최적화

## 유형

### 클라이언트 측 캐싱

브라우저 등에서 데이터 저장. 서버 요청 감소.
예: 웹 브라우저 캐시, 쿠키, 로컬 스토리지

### 서버 측 캐싱

서버에서 데이터 저장. DB나 외부 API 요청 감소.
예: 메모리 캐시, 파일 시스템 캐시

### 프록시 캐싱

중간 서버에서 데이터 저장. 클라이언트-서버 간 트래픽 감소.
예: CDN, 리버스 프록시

## 전략

- 캐시 적중률 최적화
- 캐시 미스 처리
- 데이터 만료 관리
- 캐시 무효화 구현
- 프리캐칭 활용

## 도구와 라이브러리

### 메모리 캐시

- Redis: 다양한 데이터 구조 지원 인메모리 저장소
- Memcached: 분산 메모리 객체 캐싱 시스템

### 디스크 캐시

- Varnish: HTTP 리버스 프록시 캐시
- Squid: 웹 프록시 캐싱 서버

### 애플리케이션 캐시

- Ehcache: Java용 오픈 소스 캐싱 라이브러리
- Caffeine: Java 8+ 고성능 캐싱 라이브러리

## 예시

### Redis를 이용한 서버 측 캐싱 (Python)

```python
import redis
import time

cache = redis.StrictRedis(host='localhost', port=6379, db=0)

def get_data_from_source(key):
    time.sleep(2)
    return f"Data for {key}"

def get_data(key):
    data = cache.get(key)
    if data:
        return data.decode('utf-8')
    
    data = get_data_from_source(key)
    cache.set(key, data, ex=60)
    return data

key = "example_key"
print(get_data(key))  # 첫 요청: 데이터 소스에서 가져옴
print(get_data(key))  # 두 번째 요청: 캐시에서 가져옴
```

### 브라우저 캐싱 (HTTP 헤더 설정)

```http
HTTP/1.1 200 OK
Content-Type: text/html
Cache-Control: max-age=3600, must-revalidate
Expires: Wed, 21 Oct 2020 07:28:00 GMT

<html>
<head>
    <title>Example Page</title>
</head>
<body>
    <h1>Hello, World!</h1>
</body>
</html>
```

## 장점

- 시스템 성능 향상
- 응답 시간 단축으로 사용자 경험 개선
- 자원 사용 최적화
- 서버 및 네트워크 부하 감소

## 단점

- 데이터 일관성 유지 어려움
- 캐시 무효화 로직의 복잡성
- 추가 메모리 자원 필요

## 사용 사례

- 웹 애플리케이션의 정적 자원 및 API 응답 캐싱
- 데이터베이스 쿼리 결과 캐싱
- CDN을 통한 전 세계 분산 콘텐츠 제공
- 모바일 앱의 로컬 데이터 캐싱

캐싱은 다양한 애플리케이션에서 성능 향상과 응답 시간 단축을 위한 필수 기술. 사용자 경험 개선과 시스템 효율성 증대에 크게 기여함.
