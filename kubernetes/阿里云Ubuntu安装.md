kubernetes 1.11.0

在阿里云上准备了三台机器：

角色 | 主机名 | 外网IP地址 | 内网IP地址 | 安装服务
---- | --- | --- | --- | ---
Master | clic_k8s_master | 42.92.173.92|172.26.90.75 | kube-apiserver kube-controller-manager kube-scheduler etcd(2.2.5)
Node | clic_k8s_node1 | 47.92.102.90|172.26.90.72 | kubelet kube-proxy docker flannel
Node | clic_k8s_node2 | 47.92.167.112|172.26.90.73 | kubelet kube-proxy docker flannel

### Master安装：
1. 添加源，由于Google源(https://packages.cloud.google.com/apt/doc/apt-key.gpg) 被墙，转而使用阿里云镜像源
```shell
# curl -s https://mirrors.aliyun.com/kubernetes/apt/doc/apt-key.gpg | sudo apt-key add -
# echo "deb https://mirrors.aliyun.com/kubernetes/apt kubernetes-xenial main" > /etc/apt/sources.list
```
2. 后续安装参考：
* [ubuntu下使用kubeadm安装部署kubernetes v1.10](https://blog.csdn.net/qq_37423198/article/details/79762687)
* [用kubeadm在Ubuntu上快速构建Kubernetes测试集群](https://github.com/rootsongjc/kubernetes-handbook/blob/master/practice/install-kubernetes-on-ubuntu-server-16.04-with-kubeadm.md)
