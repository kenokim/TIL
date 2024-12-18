## Page #7~9
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

