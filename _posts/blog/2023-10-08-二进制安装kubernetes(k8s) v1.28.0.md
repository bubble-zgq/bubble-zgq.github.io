# 二进制安装kubernetes(k8s) v1.28.0



# 介绍

kubernetes（k8s）二进制高可用安装部署 支持ipv4+ipv6 双栈

不配置ipv6，不影响后续，不过集群依旧支持ipv6的，为后期留有扩展可能性

# 环境

| 主机名称 | IP地址       | 说明       | 软件                                                         |
| -------- | ------------ | ---------- | ------------------------------------------------------------ |
|          | 192.168.1.60 | 外网节点   | 下载各种需要的安装包                                         |
| Master01 | 192.168.0.31 | master节点 | kube-apiserver kube-controller-manage kube-scheduler,etcd kubelet kube-proxy nfs-client haproxy keepalived nginx |
| master02 | 192.168.0.32 | master节点 | kube-apiserver kube-controller-manage kube-scheduler,etcd kubelet kube-proxy nfs-client haproxy keepalived nginx |
| master03 | 192.168.0.33 | master节点 | kube-apiserver kube-controller-manage kube-scheduler,etcd kubelet kube-proxy nfs-client haproxy keepalived nginx |
| node01   | 192.168.0.34 | node节点   | kubelet kube-proxy nfs-client nginx                          |
| node02   | 192.168.0.35 | node节点   | kubelet kube-proxy nfs-client nginx                          |
|          | 192.168.0.36 | vip        |                                                              |

网段 物理机 192.168.0.0/24 service 10.96.0.0 pod 172.16.0.0/12

