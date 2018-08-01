kubernetes 1.11.0

在阿里云上准备了三台机器：

角色 | 主机名 | 外网IP地址 | 内网IP地址 | 安装服务
---- | --- | --- | --- | ---
Master | clic_k8s_master | 47.92.173.92|172.26.90.75 | kube-apiserver kube-controller-manager kube-scheduler etcd(2.2.5)
Node | clic_k8s_node1 | 47.92.102.90|172.26.90.72 | kubelet kube-proxy docker flannel
Node | clic_k8s_node2 | 47.92.167.112|172.26.90.73 | kubelet kube-proxy docker flannel

### Master安装：
1. 添加源，由于Google源(https://packages.cloud.google.com/apt/doc/apt-key.gpg) 被墙，转而使用阿里云镜像源
```shell
# curl -s https://mirrors.aliyun.com/kubernetes/apt/doc/apt-key.gpg | sudo apt-key add -
# echo "deb https://mirrors.aliyun.com/kubernetes/apt kubernetes-xenial main" > /etc/apt/sources.list
```
2. 后续安装参考：
* [Kubernetes在CentOS7下二进制文件方式安装、离线安装](https://blog.csdn.net/chen798213337/article/details/78501042)
* [ubuntu下使用kubeadm安装部署kubernetes v1.10](https://blog.csdn.net/qq_37423198/article/details/79762687)
* [用kubeadm在Ubuntu上快速构建Kubernetes测试集群](https://github.com/rootsongjc/kubernetes-handbook/blob/master/practice/install-kubernetes-on-ubuntu-server-16.04-with-kubeadm.md)


### 参考
* [Ubuntu 18.04 离线安装Kubernetes v1.11.1](https://morphyhu.szitcare.com/wordpress/?p=1139)
