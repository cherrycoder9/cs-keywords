# 서버리스 (Serverless)

서버리스는 서버 관리와 인프라 운영 부담을 덜어주고 개발자가 애플리케이션 코드와 비즈니스 로직에 집중할 수 있게 하는 클라우드 컴퓨팅 실행 모델. 클라우드 제공자가 서버 리소스를 동적으로 할당하고 관리하며, 사용량에 따라 비용이 청구됨.

## 주요 특징

- **자동 확장**: 트래픽 변화에 따른 자동 리소스 확장/축소
- **무상태 함수**: 요청마다 독립 실행되는 상태 비보존 함수
- **사용 기반 비용**: 실제 사용 리소스에 대해서만 비용 지불
- **신속한 배포**: 코드의 빠른 배포 및 업데이트 가능
- **관리 편의성**: 서버 관리 부담 감소, 코드 작성에 집중

## 핵심 구성 요소

- **서버리스 함수**: 클라우드에서 실행되는 단기 무상태 함수 (예: AWS Lambda, Azure Functions)
- **API 게이트웨이**: HTTP 요청을 서버리스 함수로 라우팅, RESTful API 제공 (예: AWS API Gateway)
- **데이터베이스**: 자동 확장/관리되는 서버리스 데이터베이스 (예: AWS DynamoDB, Firebase Firestore)
- **스토리지**: 파일 및 객체 저장/관리 서비스 (예: AWS S3, Azure Blob Storage)
- **이벤트 소스**: 서버리스 함수 트리거 (예: 클라우드 이벤트 버스, 메시지 큐, 스토리지 이벤트)

## 구현 예시

### AWS Lambda 함수 (Python)

```python
import json

def lambda_handler(event, context):
    name = event.get('name', 'World')
    message = f"Hello, {name}!"
    return {
        'statusCode': 200,
        'body': json.dumps({'message': message})
    }
```

### AWS CLI를 통한 Lambda 함수 배포

```sh
# 함수 패키징
zip function.zip lambda_function.py

# Lambda 함수 생성
aws lambda create-function \
    --function-name myLambdaFunction \
    --zip-file fileb://function.zip \
    --handler lambda_function.lambda_handler \
    --runtime python3.8 \
    --role arn:aws:iam::123456789012:role/execution_role

# API Gateway 설정
aws apigateway create-rest-api --name 'My API'
aws apigateway get-resources --rest-api-id <api-id>
aws apigateway put-method \
    --rest-api-id <api-id> \
    --resource-id <resource-id> \
    --http-method GET \
    --authorization-type NONE
aws apigateway put-integration \
    --rest-api-id <api-id> \
    --resource-id <resource-id> \
    --http-method GET \
    --type AWS_PROXY \
    --integration-http-method POST \
    --uri 'arn:aws:apigateway:<region>:lambda:path/2015-03-31/functions/arn:aws:lambda:<region>:123456789012:function:myLambdaFunction/invocations'
aws apigateway create-deployment --rest-api-id <api-id> --stage-name prod
```

## 장점

- **비용 효율성**: 사용량 기반 과금으로 유휴 리소스 비용 없음
- **자동 확장**: 트래픽에 따른 자동 확장/축소로 성능과 비용 최적화
- **빠른 개발 주기**: 인프라 관리 부담 감소로 신속한 개발 및 배포
- **유지보수 용이**: 인프라 관리 불필요로 코드 집중 가능

## 단점

- **제한된 실행 시간**: 함수 실행 시간 제한 (예: AWS Lambda 최대 15분)
- **콜드 스타트 지연**: 장기 미호출 함수의 초기 호출 시 지연 발생
- **디버깅 난이도**: 무상태 함수 특성상 디버깅 어려움, 분산 로그 관리 필요
- **종속성 이슈**: 특정 클라우드 제공자에 대한 종속 가능성

## 활용 사례

- **백엔드 API**: 사용자 요청 처리 백엔드 API 구현
- **데이터 처리**: 이벤트 기반 데이터 처리 작업 구성
- **파일 처리**: 업로드 파일 처리 및 변환 작업 수행
- **알림 서비스**: 이벤트 발생 시 알림 전송 서비스 구현
- **웹 애플리케이션**: 정적 웹사이트와 백엔드 로직 호스팅

서버리스 아키텍처는 인프라 관리 부담을 줄이고 신속한 애플리케이션 개발 및 배포 환경을 제공함. 개발자의 비즈니스 로직 집중을 가능케 하며 운영 효율성을 높임.
