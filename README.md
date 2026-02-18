# kubernetes-multi-node-cluster-setup

## Create token to join the cluster. 
kubeadm token create --print-join-command
<img width="1420" height="88" alt="image" src="https://github.com/user-attachments/assets/0f7a9c18-26f6-45a3-aeb4-1a2a847f73d0" />

## Join the cluster  - Change the ip of your master node. 
kubeadm join 172.31.32.234:6443 --token ti1dko.2izx151047hz9jkm --discovery-token-ca-cert-hash sha256:0b356dbb5454f7707267e5d674e0f936b1b872c1e76c8950a2b8f27134383ae3

<img width="1420" height="343" alt="image" src="https://github.com/user-attachments/assets/9a14f7a5-c5b8-457f-a40d-b97935f8f56e" />
