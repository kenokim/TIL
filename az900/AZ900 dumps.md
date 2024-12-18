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



## NSG
- NSG 는 vnet 에서 network traffic 을 필터링하는 가상 방화벽이다.
- Subnet 을 대상으로 적용되며, inbound, outbound 트래픽을 port, ip, protocol 등의 조건에 따라 제어한다.

  
