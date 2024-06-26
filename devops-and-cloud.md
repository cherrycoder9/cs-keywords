# Devops and cloud

## [가상화 (Virtualization)](https://github.com/cherrycoder9/cs-keywords/blob/main/devops-and-cloud/virtualization.md)

- 물리적 하드웨어를 다수의 논리적 자원으로 분할하여 공유하는 기술
- 자원 활용율 제고, 비용 절감, 유연한 인프라 운영 등의 이점 제공

## [컨테이너 (Container)](https://github.com/cherrycoder9/cs-keywords/blob/main/devops-and-cloud/container.md)

- 애플리케이션과 종속성을 패키지화하여 격리된 환경에서 실행하는 기술
- 이식성과 확장성이 뛰어나며, 간편한 배포와 관리가 가능함

## [도커 (Docker)](https://github.com/cherrycoder9/cs-keywords/blob/main/devops-and-cloud/docker.md)

- 컨테이너 생성, 실행, 배포를 위한 오픈소스 플랫폼
- 컨테이너 이미지 관리 도구와 레지스트리를 통한 이미지 공유 기능 제공

## [쿠버네티스 (Kubernetes)](https://github.com/cherrycoder9/cs-keywords/blob/main/devops-and-cloud/kubernetes.md)

- 컨테이너 오케스트레이션을 위한 오픈소스 플랫폼
- 컨테이너 배포, 확장, 관리 자동화와 함께 복구, 로드 밸런싱 등의 기능 지원

## [마이크로서비스 (Microservices)](https://github.com/cherrycoder9/cs-keywords/blob/main/devops-and-cloud/microservices.md)

- 애플리케이션을 작고 독립적인 서비스 단위로 분해하는 아키텍처 패턴
- 각 서비스는 단일 책임을 가지며, 느슨한 결합을 통해 유연성과 확장성 확보

## [서버리스 (Serverless)](https://github.com/cherrycoder9/cs-keywords/blob/main/devops-and-cloud/serverless.md)

- 서버 관리 없이 코드 실행에 집중할 수 있는 클라우드 컴퓨팅 모델
- 사용량에 따른 과금, 자동 확장, 높은 가용성 등의 특징을 가짐

## [CI/CD (Continuous Integration/Continuous Delivery)](https://github.com/cherrycoder9/cs-keywords/blob/main/devops-and-cloud/cicd.md)

- 코드 변경사항의 지속적 통합, 테스트, 배포를 자동화하는 개발 및 운영 방식
- 개발 주기 단축, 품질 개선, 신속한 피드백 반영 등의 효과를 얻을 수 있음

## 클라우드 컴퓨팅 (Cloud Computing)

- 인터넷을 통해 IT 자원을 온디맨드로 제공하는 컴퓨팅 모델
- 초기 투자 비용 절감, 유연한 자원 활용, 확장성 등의 장점 제공

## IaaS (Infrastructure as a Service)

- 서버, 스토리지, 네트워크 등 인프라를 서비스로 제공하는 클라우드 모델
- 사용자가 인프라를 직접 제어하고 관리할 수 있는 유연성 제공

## PaaS (Platform as a Service)

- 애플리케이션 개발 및 배포를 위한 플랫폼을 서비스로 제공하는 클라우드 모델
- 사용자는 애플리케이션 개발에 집중하고, 인프라 관리는 PaaS 제공자가 담당

## SaaS (Software as a Service)

- 소프트웨어를 서비스 형태로 제공하는 클라우드 모델
- 사용자는 웹 브라우저를 통해 소프트웨어를 이용하며, 설치와 유지보수 부담 경감

## DevOps

- 개발과 운영을 통합하여 소프트웨어 개발, 배포, 운영 프로세스를 자동화하고 최적화하는 문화와 방법론
- 신속한 개발 주기와 안정적 운영, 지속적 개선을 추구함

## 모니터링 (Monitoring)

- 시스템과 애플리케이션의 상태와 성능을 실시간으로 감시하고 분석하는 활동
- 시스템 안정성 확보와 신속한 이슈 대응을 위해 필수적임

## 로깅 (Logging)

- 시스템 및 애플리케이션에서 발생하는 이벤트, 에러, 상태 변화 등을 기록하는 활동
- 문제 해결, 성능 분석, 감사 등에 활용할 수 있는 중요한 정보를 제공함

## 인프라 자동화 (Infrastructure Automation)

- IT 인프라의 프로비저닝, 구성, 배포, 관리 등을 자동화하는 기술
- 수작업 오류 감소, 효율성 향상, 일관된 인프라 관리를 가능케 함

## 구성 관리 (Configuration Management)

- 소프트웨어와 시스템의 구성 정보를 일관되고 체계적으로 관리하는 프로세스
- 시스템 일관성과 안정성, 추적성 확보에 필수적임

## Ansible

- YAML 기반의 간결한 문법을 사용하는 오픈소스 구성 관리 및 자동화 도구
- SSH를 통해 에이전트 없이 원격 시스템을 관리할 수 있음

## Chef

- Ruby 기반의 DSL을 사용하는 오픈소스 구성 관리 도구
- 유연성과 확장성이 뛰어나 복잡한 인프라 관리에 적합함

## Puppet

- 독자적인 선언형 언어를 사용하는 오픈소스 구성 관리 도구
- 강력한 기능과 다양한 플랫폼 지원으로 대규모 인프라 관리에 적합함

## 배포 파이프라인 (Deployment Pipeline)

- 코드 변경부터 운영 환경 배포까지의 자동화된 프로세스
- 개발 속도 향상, 안정적 배포, 운영 오류 감소 등의 효과를 얻을 수 있음

## 오케스트레이션 (Orchestration)

- 복잡한 시스템의 구성 요소들을 자동화된 방식으로 조정하고 관리하는 작업
- 배포, 설정 관리, 자원 할당 등의 자동화로 운영 효율성을 높임

## 인프라 관리 (Infrastructure Management)

- IT 시스템을 구성하는 하드웨어와 소프트웨어 인프라를 관리하는 활동
- 안정적인 운영, 성능 최적화, 가용성과 보안 유지를 목표로 함

## 애플리케이션 성능 관리 (Application Performance Management, APM)

- 애플리케이션의 성능을 모니터링하고 분석하여 병목 현상을 식별하고 해결하는 작업
- 사용자 경험 향상, 애플리케이션 안정성 확보, 자원 활용 효율화에 기여함

## 로그 관리 (Log Management)

- 애플리케이션과 시스템에서 생성되는 로그 데이터를 수집, 저장, 분석, 시각화하는 활동
- 장애 진단, 성능 분석, 보안 감사, 시스템 동작 이해 및 문제 해결에 활용됨

## 모니터링 도구 (Monitoring Tools)

- 시스템과 애플리케이션의 가용성, 성능, 상태 등을 실시간으로 감시하고 이상 징후를 탐지하는 도구
- 시스템 안정성 유지, 신속한 문제 대응, 성능 병목 현상 파악 및 개선에 도움을 줌

## 알림 (Alert)

- 모니터링 시스템에서 설정한 조건에 따라 이상 상황 발생 시 담당자에게 알림을 전송하는 기능
- 신속한 문제 인지와 대응, 시스템 다운타임 최소화, 피해 확산 방지에 기여함
