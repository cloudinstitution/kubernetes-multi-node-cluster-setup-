# kubernetes-multi-node-cluster-setup

## Make sure to enable 6443 port in the security group

<img width="1209" height="468" alt="image" src="https://github.com/user-attachments/assets/7fc5e558-ddf7-4c45-8e82-841cbde96663" />

## Initialize a Kubernetes cluster using the kubeadm

$ kubeadm init --pod-network-cidr=10.244.0.0/16

## install CNI 

$ kubectl apply -f https://raw.githubusercontent.com/flannel-io/flannel/master/Documentation/kube-flannel.yml


## To start using your cluster, you need to run the following as a regular user

$ mkdir -p $HOME/.kube 

$ sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config

$ sudo chown $(id -u):$(id -g) $HOME/.kube/config

kubectl taint nodes --all node-role.kubernetes.io/control-plane-



## Create token to join the cluster. 
kubeadm token create --print-join-command
<img width="1420" height="88" alt="image" src="https://github.com/user-attachments/assets/0f7a9c18-26f6-45a3-aeb4-1a2a847f73d0" />

## Join the cluster  - Change the ip of your master node. 
kubeadm join 172.31.32.234:6443 --token ti1dko.2izx151047hz9jkm --discovery-token-ca-cert-hash sha256:0b356dbb5454f7707267e5d674e0f936b1b872c1e76c8950a2b8f27134383ae3

<img width="1420" height="343" alt="image" src="https://github.com/user-attachments/assets/9a14f7a5-c5b8-457f-a40d-b97935f8f56e" />

## Verify the cluster nodes using  # kubectl get nodes

<img width="1358" height="148" alt="image" src="https://github.com/user-attachments/assets/c325c795-680d-4178-a26c-498322ae4c94" />


## Verify the cluster components 

kubectl get --raw='/readyz?verbose'
<img width="1420" height="746" alt="image" src="https://github.com/user-attachments/assets/10751628-1ab3-467f-8f11-af5cd31807d7" />



