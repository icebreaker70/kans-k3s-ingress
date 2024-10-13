# 개요
- 목적 : MacBook M 시리즈에 vagrant 이용하여 k3s cluster 구성
- 준비사항 : VMware Fusion과 vagrant 설치 필요함

# 소스 Download
❯ git clone https://github.com/icebreaker70/kans-k3s-ingress
❯ cd kans-k3s-ingress

# VM(노드) 생성
❯ vagrant up --provision

# VM 상태 확인
❯ vagrant status
Current machine states:

k3s-s                     running (vmware_desktop)
k3s-w1                    running (vmware_desktop)
k3s-w2                    running (vmware_desktop)
k3s-w3                    running (vmware_desktop)

# VM 접속
❯ vagrant ssh k3s-s
❯ vagrant ssh k3s-w1
❯ vagrant ssh k3s-w2
❯ vagrant ssh k3s-w3

# k3s cluster 확인
❯ vagrant ssh k3s-s
$ kc cluster-info      # kc는 kubectl 실행 내용을 Color로 보여주는 Tool의 Alias
$ kc get nodes -o wide
$ kc get pods -A

# vm 일시멈춤
❯ vagrant suspend

# vm 멈춤재개
❯ vagrant resume

# vm 삭제
❯ vagrant destory -f
