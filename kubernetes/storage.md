## dynamic volume provisioning
- storageClass 생성 -> cluster 에 생성되는 객체
- dynamic provisioner: pvc -> 스토리지 요청 확인 -> volume driver 를 사용해 volume 생성 -> pvc 와 연결
- pv 의 lifecycle 은 pvc recreation policy 에 의해 결정되고, 기본은 pod 와 같다.
