# 컨테이너 (Container)

컨테이너는 응용 프로그램과 그 실행 환경을 패키징하여 격리된 공간에서 구동하는 가상화 기술. 호스트 OS 커널을 공유하면서도 독립적인 실행 환경을 제공함.

## 주요 특징

- **경량성**: 하이퍼바이저 기반 가상화보다 리소스 사용량이 적고, 신속한 시작과 종료 가능
- **이식성**: 응용 프로그램과 필요 라이브러리를 포함한 이미지로 다양한 환경에서 일관된 동작 보장
- **격리성**: 각 컨테이너는 독립적인 파일 시스템, 네트워크, 프로세스 공간을 가짐
- **확장성**: 오케스트레이션 도구를 통해 대규모 컨테이너 효율적 관리 및 확장

## 핵심 구성 요소

- **컨테이너 이미지**: 응용 프로그램과 실행 환경을 정의한 실행 가능한 패키지
- **컨테이너 런타임**: 이미지를 실행하고 관리하는 소프트웨어 (예: Docker)
- **컨테이너 레지스트리**: 이미지를 저장하고 배포하는 저장소 (예: Docker Hub)

## Docker 활용 예시

### Dockerfile 작성

```dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["python", "app.py"]
```

### 이미지 빌드 및 실행

```sh
docker build -t my-python-app .
docker run -d -p 5000:5000 my-python-app
```

## 컨테이너 오케스트레이션

다수의 컨테이너를 효율적으로 관리하고 배포하는 기술. 주요 도구로 Kubernetes, Docker Swarm, Apache Mesos 등이 있음.

### Kubernetes 예시

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-python-app
spec:
  replicas: 3
  selector:
    matchLabels:
      app: my-python-app
  template:
    metadata:
      labels:
        app: my-python-app
    spec:
      containers:
      - name: my-python-app
        image: my-python-app:latest
        ports:
        - containerPort: 5000
```

## 장점

- **리소스 효율성**: 경량화된 실행 환경으로 자원 활용 최적화
- **신속한 배포**: 일관된 환경 제공으로 빠르고 안정적인 배포 실현
- **높은 이식성**: 개발 환경과 운영 환경의 격차 해소
- **강력한 격리**: 응용 프로그램 간 간섭 최소화

## 활용 사례

- **마이크로서비스**: 각 서비스를 독립 컨테이너로 배포하여 관리
- **CI/CD**: 빌드, 테스트, 배포 과정에 컨테이너 활용으로 일관성 및 효율성 향상
- **데이터 처리**: 데이터 파이프라인을 컨테이너로 구성해 유연성과 확장성 확보
- **애플리케이션 샌드박싱**: 격리 환경에서 애플리케이션 실행으로 보안성 강화

컨테이너는 현대 소프트웨어 개발과 배포의 핵심 도구로, 애플리케이션의 이식성, 확장성, 효율성을 크게 향상시킴. 개발자와 운영 팀의 협업을 원활하게 하고, 신속하고 안정적인 배포를 실현함.
