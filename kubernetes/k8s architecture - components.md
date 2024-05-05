## Components
- kubernetes 클러스터는 1개의 master node 와 여러 개의 worker node 로 구성된다.
- master node 는 control plane components 를 실행한다.
- worker node 는 각각 worker node components 를 실행한다.
- 이러한 components 는 pod 로서 실행된다.

## control plane components
### kube-apiserver
- control-plane 의 진입점으로 rest, kubectl, kubeadm 과 같은 cli 를 통해 api 에 접근한다.
### kube-scheduler
- 클러스터의 상태를 확인하고 pod 의 리소스 요구를 고려하여 스케쥴링한다.
### kube-controller-manager
- 클러스터의 controller object 를 관리한다.
### etcd
- 분산형 key-value 스토리지로 클러스터 데이터를 저장한다.
- 예를 들어, manifest 파일을 저장한다.

## worker node components
### container runtime engine
- 각 노드는 containerd 와 같은 런타임 엔진을 실행한다. (pod 아님)
### kubelet
- 각 노드가 control plane 과 통신하기 위한 작은 애플리케이션이다.
### kube-proxy
- daemonset 으로 배포된 프록시 서버로 각 노드의 파드와 내부/외부 요소들과의 통신을 관리한다.
