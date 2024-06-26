# Performance and scalability

## [성능 측정 (Performance Measurement)](https://github.com/cherrycoder9/cs-keywords/blob/main/performance-and-scalability/performance-measurement.md)

- 응답 시간, 처리량 등 시스템이나 애플리케이션의 성능 지표를 측정하는 활동
- 성능 현황 파악 및 개선 목표 설정에 필요한 객관적 데이터를 수집함

## [성능 분석 (Performance Analysis, 프로파일링)](https://github.com/cherrycoder9/cs-keywords/blob/main/performance-and-scalability/performance-analysis.md)

- 성능 측정 데이터를 분석하여 병목 지점과 성능 저하 요인을 식별하는 프로세스
- 정확한 문제 진단과 효과적인 최적화 전략 수립에 활용됨

## [성능 최적화 (Performance Optimization)](https://github.com/cherrycoder9/cs-keywords/blob/main/performance-and-scalability/performance-optimization.md)

- 코드, 아키텍처, 설정 등을 조정하여 시스템 성능을 개선하는 작업
- 자원 사용량을 최소화하면서 처리 속도를 높이는 것이 주요 목표임

## [로드 밸런싱 (Load Balancing)](https://github.com/cherrycoder9/cs-keywords/blob/main/performance-and-scalability/load-balancing.md)

- 여러 서버로 트래픽을 분산시켜 시스템의 가용성과 확장성을 높이는 기술
- 단일 실패점 제거, 부하 분산, 응답 시간 단축 등의 효과를 얻을 수 있음

## [캐싱 (Caching)](https://github.com/cherrycoder9/cs-keywords/blob/main/performance-and-scalability/caching.md)

- 빈번히 액세스되는 데이터를 고속 저장소에 보관하여 성능을 향상시키는 기법
- DB 쿼리나 API 호출 횟수를 줄여 응답 시간을 단축하고 백엔드 부하를 완화함

## CDN (Content Delivery Network)

- 콘텐츠를 사용자와 가까운 서버에 분산 배포하여 전송 속도를 높이는 시스템
- 지리적으로 분산된 사용자에게 일관되고 신속한 콘텐츠 제공이 가능해짐

## 수평적 확장 (Horizontal Scaling, 스케일 아웃)

- 동일 사양의 서버를 추가하여 처리 능력을 선형적으로 늘리는 방식  
- 유연한 확장이 가능하며 분산 시스템 구축에 적합함

## 수직적 확장 (Vertical Scaling, 스케일 업)

- 단일 서버의 하드웨어 성능을 업그레이드하여 처리 용량을 증대시키는 방법
- 간단히 적용 가능하나 확장 한계가 있어 장기적 관점에서는 한계가 있음

## 데이터베이스 인덱싱 (Database Indexing)

- DB 테이블에 인덱스를 생성하여 데이터 검색 및 쿼리 속도를 높이는 기술
- 대용량 데이터 처리 시 쿼리 성능 향상에 필수적인 요소임

## 비동기 처리 (Asynchronous Processing)

- 요청 후 응답을 기다리지 않고 다른 작업을 수행하는 방식
- 자원 활용도와 응답성 향상에 도움되지만 복잡도 증가와 동시성 이슈 고려 필요

## 코드 최적화 (Code Optimization)

- 실행 속도, 메모리 사용량, 코드 크기 등을 개선하는 작업
- 성능 향상과 자원 효율화에 기여하나 가독성 저하 방지가 중요함

## 지연 로딩 (Lazy Loading)

- 리소스가 실제 필요한 시점까지 로딩을 미루는 기법
- 초기 로딩 속도 개선과 불필요한 자원 낭비 방지에 효과적임

## 샤딩 (Sharding)

- 큰 데이터베이스를 작은 단위로 분할하여 저장하고 관리하는 기술
- 부하 분산과 확장성 향상으로 대용량 데이터 처리에 유리함

## 레플리케이션 (Replication)

- 동일한 데이터를 다중 위치에 복제하여 저장하는 기술
- 가용성과 내결함성 강화, 지역별 사용자 응답 속도 개선에 도움됨

## 큐 (Queue)

- 데이터를 순차적으로 저장하고 처리하는 자료구조
- 비동기 작업, 메시지 전달, 작업 순서 유지 등에 널리 사용됨

## 메시지 브로커 (Message Broker)

- 애플리케이션 사이에서 메시지 교환을 중개하고 관리하는 시스템
- 비동기 통신과 시스템 결합도 완화, 데이터 정합성 유지에 기여함

## 분산 시스템 (Distributed System)

- 네트워크로 연결된 다수의 컴퓨터가 하나의 시스템처럼 동작하는 구조
- 단일 시스템의 한계를 극복하고 확장성, 가용성을 높일 수 있음

## CAP 정리 (CAP Theorem)

- 분산 시스템에서 일관성, 가용성, 분할 내성을 동시에 보장할 수 없다는 이론
- 시스템 요구사항에 맞게 두 가지 속성을 선택하여 설계해야 함
