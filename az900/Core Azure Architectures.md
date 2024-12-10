## regions
- 최소 3개의 데이터센터를 묶는 영역

### region pair
- 각 region 은 region pair 를 가지며, 이는 fastest connection 을 제공하는 region 이다.

### soverign azure
- 가입을 위해 허가가 필요하다.
- Azure government 등이 있다.

## availability zone (AZ, 가용성 영역)
- 하나의 region 내에 있는 물리적으로 격리된 1 or more datacenters
  - 모든 region 이 AZ를 가지지는 않는다.
  - 모든 service 가 AZ를 지원하지는 않는다.

## 3 types of AZ services
1. zonal services: 어느 AZ 에 배포할 지 선택할 수 있다.
  - ex). VM
2. zone redundant services: 자동으로 여러 AZ 에 배포하여 관리된다.
  - ex). cosmosdb
3. always available services: region, AZ 에 상관없이 가용된다.
  - ex). portal, entra id, front door

## resource hierarchy
- management group -> subscriptions -> rg -> resource

## availability sets (가용성 집합)
- VM 의 고가용성을 보장하기 위해 구성된다.

