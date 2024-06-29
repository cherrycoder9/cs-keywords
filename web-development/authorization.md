# 인가 (Authorization)

인가는 인증 후 사용자에게 시스템 내 특정 자원이나 기능에 대한 접근 권한을 부여하는 과정. 사용자의 신원 확인 후, 허용된 작업을 결정함. 시스템 자원 보호와 무단 접근 방지를 위한 핵심 보안 요소.

## 주요 특징

- **접근 제어**: 특정 자원/기능 접근 가능 여부 결정
- **정책 기반**: 미리 정의된 정책과 규칙에 따른 접근 제어
- **역할 기반**: 사용자 역할에 따른 권한 부여로 관리 효율성 증대

## 주요 개념

### 1. 역할 기반 접근 제어 (RBAC)

사용자 역할에 따라 접근 권한 부여.

```python
roles = {
    'admin': ['read', 'write', 'delete'],
    'user': ['read', 'write'],
    'guest': ['read']
}

def check_access(role, action):
    return action in roles.get(role, [])

# 사용 예시
print(check_access('admin', 'delete'))  # True
print(check_access('user', 'delete'))   # False
```

### 2. 속성 기반 접근 제어 (ABAC)

사용자, 자원, 환경의 속성 기반으로 접근 권한 부여. 세밀하고 유연한 제어 가능.

```python
def check_access(user, resource, action):
    if user['role'] == 'admin':
        return True
    if (resource['type'] == 'document' and
        action == 'read' and
        user['department'] == resource['owner_department']):
        return True
    return False

# 사용 예시
user = {'role': 'user', 'department': 'sales'}
resource = {'type': 'document', 'owner_department': 'sales'}
print(check_access(user, resource, 'read'))   # True
print(check_access(user, resource, 'delete')) # False
```

### 3. 접근 제어 목록 (ACL)

각 자원에 대해 접근 권한을 명시적으로 설정.

```python
acl = {
    'document1': {'read': ['alice', 'bob'], 'write': ['alice']},
    'document2': {'read': ['bob'], 'write': ['bob']}
}

def check_access(user, resource, action):
    return user in acl.get(resource, {}).get(action, [])

# 사용 예시
print(check_access('alice', 'document1', 'read'))  # True
print(check_access('bob', 'document1', 'write'))   # False
```

## 주요 요소

- **정책 (Policy)**: 접근 권한 정의 규칙/조건
- **역할 (Role)**: 특정 권한을 가진 사용자 그룹
- **권한 (Permission)**: 특정 자원에 대해 수행 가능한 작업
- **사용자 (User)**: 시스템 접근 개체
- **자원 (Resource)**: 보호 대상 데이터/기능

## 중요성

- **보안 강화**: 무단 접근 방지
- **데이터 보호**: 중요 데이터/자원의 변경/손실 방지
- **관리 효율성**: 역할 기반 접근 제어로 효율적 권한 관리
- **컴플라이언스**: 법적 규제/정책 준수로 시스템 신뢰성 향상

## 활용 사례

- **기업 내부 시스템**: 직원 역할별 접근 권한 부여
- **웹 애플리케이션**: 사용자 유형별 기능 접근 제한
- **API 접근 제어**: 인증된 사용자의 자원 접근 관리
- **클라우드 서비스**: 사용자/앱 역할별 클라우드 자원 접근 제어

인가 시스템은 보안의 핵심 요소로, 인증된 사용자의 허용된 작업 수행을 보장함. 이를 통해 시스템 보안성을 강화하고 중요 데이터/자원을 보호함.
