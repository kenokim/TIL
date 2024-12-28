## 리소스 관리 계층
- 상속되는 것: RBAC, policy, locks
- 상속되지 않는 것: tags, 설정, 비용 관리
- 이 값들은 management group, subscription, resource group, resource 레벨에서 상속된다.

## storage redundancy
- LRS: replicates 3 in a data center
- ZRS: replicates 3 in a region
- GRS: replicates within multiple regions, LRS for each
- GZRS: replicates within multiple regions, ZRS for each

## VM scaling
### vmss
- load balanced, identical vm sets 를 자동으로 배포, 스케일 아웃/인 하는 기능이다.
- aks 에서 node pool 을 관리하는 mechanism 이다.

### availability set
- 직접 수동으로 vm scale 을 관리하는 기능이다.

### devtest labs
- ARM template 을 통해 vm 생성/삭제 등 쉽게 관리할 수 있는 서비스이다.

## File storage
- Hierarchical structure with folders
- mount to server, use as a drive (D.drive)
- supports SMB (cross-platform), NFS (linux) protocols

## Azure workspaces
- Web based: Azure portal, Azure cloud shell (bash, ps)
- Local tools: Azure cli

## Azure 보안 계층 정리

| **보안 계층**              | **역할**                          | **적용 대상**               |
|----------------------------|-----------------------------------|------------------------------|
| **NSG**                   | 포트/프로토콜/IP 필터링           | 서브넷 및 VM NIC            |
| **Azure DDoS Protection** | DDoS 공격 방어                   | 퍼블릭 IP                  |
| **Azure Firewall**        | 상태 저장 방화벽, URL 필터링      | 가상 네트워크 경계           |
| **Application Gateway**   | HTTP/HTTPS 요청 필터링, WAF 기능 | 웹 애플리케이션 트래픽      |
| **VPN Gateway/ExpressRoute** | 하이브리드 연결 및 암호화      | 온프레미스 ↔ Azure 연결     |

## Traffic manager
- 같은 DNS 을 여러 region 으로 분산한다.
- 이에 대한 failover, routing 등 기능을 제공한다.

### compliance manager
- Compliance Manager(준수 관리자)**는 Microsoft Purview의 일부로, 보안 및 규정 준수 관리 도구입니다. 기업의 규제 요구 사항 충족 여부를 평가하고 관리하도록 설계된 Azure 및 Microsoft 365 서비스입니다.
- 이를 통해 데이터 보호, 보안, 개인 정보 보호, 규제 준수 상태를 자동 평가하고, 권장 작업과 감사 보고서 생성 기능을 제공합니다.

## Azure Support Plans

| **플랜**            | **비용**      | **기술 지원**       | **응답 시간 (심각)** | **주요 대상**            |
|-------------------|--------------|-------------------|--------------------|----------------------|
| **Basic**         | 무료          | 없음               | 없음               | 개인/개발자           |
| **Developer**     | 약 $29/월     | 이메일 지원         | 8시간 이내          | 비프로덕션 환경        |
| **Standard**      | 약 $100/월    | 24/7 전화/이메일    | 1시간 이내          | 프로덕션 환경         |
| **ProDirect**     | 약 $1,000/월  | 심층적 지원         | 1시간 이내          | 대기업/중요 서비스     |

## NSG
- NSG 는 vnet 에서 network traffic 을 필터링하는 가상 방화벽이다.
- Subnet 을 대상으로 적용되며, inbound, outbound 트래픽을 port, ip, protocol 등의 조건에 따라 제어한다.

### Azure policy
- 특정 조건에 따라 Azure 리소스를 허용하거나 제한하는 정책을 정의.
- 리소스 그룹, 구독, 관리 그룹 등에 정책을 할당.
- 적용 후에 새로 생성되거나 수정되는 경우에만 적용이 된다.
- Effect 를 설정하여, 정책에 위반될 경우 어떻게 조치할 지 설정할 수 있다.

## Entra ID
- tenant 가 같은 경우 리소스를 subscription 간에 이동할 수 있다.

### Support request
- 특수한 경우에 요청을 통해 작업을 할 수 있다.

### 네트워크 과금 관련
- 인바운드 데이터 전송: 무료.
- 아웃바운드 데이터 전송: 전송량에 따라 요금 발생.
- VNet 간 전송: 같은 리전 내는 저렴, 다른 리전 간은 더 높은 비용.
- VPN Gateway와 ExpressRoute: 고정 요금 + 데이터 전송 요금.

## Azure managed disks
- premium ssd, standard ssd, standard hdd 와 같은 디스크 타입들
- Azure vm 에서 os 디스크, 데이터 디스크로 활용 가능하다.
- Blob storage 기반으로 복제나 관리가 Azure 에서 처리된다.

### service health
- Azure 서비스 전반의 가용성에 대해 확인할 수 있다.

### Azure advisor
- 비용 최적화 (Cost Optimization)
- 보안(Security)
- 고가용성(Availability)
- 성능(Performance)
- 위의 4가지 측면에서 조언을 준다.

### SLA, SLO, SLI
| **항목** | **설명**                                      | **대상**              |
|----------|----------------------------------------------|-----------------------|
| **SLA**  | 고객과 체결된 공식 계약.                      | 서비스 제공자 ↔ 고객  |
| **SLO**  | SLA를 달성하기 위한 구체적인 내부 목표.         | 내부 팀               |
| **SLI**  | SLA와 SLO를 모니터링하기 위한 측정 지표.        | 서비스 제공자          |

- SLA 를 지키지 못하는 경우, account 에 credit 을 지급한다.


