# 쿠버네티스 (Kubernetes)

쿠버네티스는 컨테이너화된 애플리케이션의 배포, 확장, 관리를 자동화하는 오픈소스 플랫폼. Google이 개발하고 현재 CNCF에서 관리함. 다양한 클라우드 환경과 온프레미스에서 컨테이너 오케스트레이션을 지원함.

## 주요 특징

- **자동화된 배포/확장**: 애플리케이션 배포와 확장 자동화로 운영 복잡성 감소
- **셀프 힐링**: 장애 발생 컨테이너 자동 재시작 또는 교체
- **서비스 디스커버리/로드 밸런싱**: 컨테이너 간 통신 간소화 및 트래픽 분산
- **비밀/구성 관리**: 애플리케이션의 민감 정보와 설정 안전 관리
- **다양한 스토리지 지원**: 로컬, 클라우드 등 다양한 스토리지 시스템과 통합

## 핵심 구성 요소

- **클러스터**: 쿠버네티스의 기본 단위, 여러 노드로 구성
- **노드**: 컨테이너 실행 단위, 마스터와 워커로 구분
- **팟**: 배포의 최소 단위, 하나 이상의 컨테이너로 구성
- **디플로이먼트**: 팟의 배포와 관리를 담당하는 컨트롤러
- **서비스**: 팟에 대한 네트워크 접근 제공 및 로드 밸런싱 지원
- **컨피그맵/시크릿**: 애플리케이션 설정 정보 관리 객체

## 사용 예시

### 디플로이먼트 구성

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

### 서비스 구성

```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-python-app-service
spec:
  selector:
    app: my-python-app
  ports:
  - protocol: TCP
    port: 80
    targetPort: 5000
  type: LoadBalancer
```

### 주요 명령어

- 클러스터 정보: `kubectl cluster-info`
- 디플로이먼트 생성: `kubectl apply -f deployment.yaml`
- 서비스 생성: `kubectl apply -f service.yaml`
- 팟 목록: `kubectl get pods`
- 디플로이먼트 업데이트: `kubectl set image deployment/my-python-app my-python-app=my-python-app:v2`
- 팟 로그: `kubectl logs <pod-name>`
- 팟 삭제: `kubectl delete pod <pod-name>`
- 디플로이먼트 삭제: `kubectl delete deployment my-python-app`
- 서비스 삭제: `kubectl delete service my-python-app-service`

## 장점

- **높은 확장성**: 수평적 확장으로 애플리케이션 부하 효율적 분산
- **유연한 환경**: 다양한 클라우드 및 온프레미스 환경에서 컨테이너 관리
- **신뢰성 향상**: 자동화된 복구와 셀프 힐링으로 높은 가용성 보장
- **자원 효율성**: 효율적인 자원 사용으로 운영 비용 절감
- **강화된 보안**: 비밀 정보와 구성의 안전한 관리 및 접근 제어

## 활용 사례

- **마이크로서비스**: 다수의 마이크로서비스 효과적 배포 및 확장
- **CI/CD**: 지속적 통합과 배포 자동화로 개발/운영 효율성 제고
- **하이브리드 클라우드**: 온프레미스와 클라우드 환경 통합으로 일관된 인프라 제공
- **데이터 처리/분석**: 대규모 데이터 처리 작업 효율적 관리 및 실행
- **개발/테스트 환경**: 일관된 환경 제공으로 개발 주기 단축

쿠버네티스는 현대 애플리케이션의 배포와 관리를 자동화하여 개발자와 운영 팀의 효율적 협업을 지원함. 이를 통해 애플리케이션의 확장성과 신뢰성을 높이고 운영의 복잡성을 줄임.
