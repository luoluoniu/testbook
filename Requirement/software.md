# 2.3 软件要求

1. 操作系统： CentOS 7.2

2. 建议全新安装系统。

3. 如果主存储采用了本地存储，考虑到计算节点存储的可扩展性，建议计算节点的本地主存储采用LVM分区，ext4文件系统，3T以上容量。如果在安装时，没有挂载大容量分区，可参考[系统存储扩容](/other-setting/enlarge-local-storage.md)的方法，对计算节点存储扩容。

4. 如果主存储不是采用Ceph存储或FusionStor存储，那么镜像服务器可以选择镜像仓库或者SFTP。考虑到镜像存储的可扩展性，建议镜像服务器(备份存储服务器)的硬盘分区采用LVM分区，ext4文件系统，3T以上容量。

5. 如果在安装时，没有挂载大容量分区，请参考[系统存储扩容](/other-setting/enlarge-local-storage.md)的方法，对镜像存储扩容。

6. 关闭selinux，配置/etc/sysconfig/selinux 并设置 SELINUX=disabled。本操作需要重启操作系统，如果用户没有设置此项，Mevoco安装时会主动配置。

7. 所有计算节点需要安装相同的操作系统，网卡的设备名称需统一，例如统一指定为eth0。CentOS 7.2系统安装后默认使用一致性网络接口配置，网卡设备名称可能并非ethx格式，建议参考[修改网卡设备编号](/other-setting/change-network-device.md)所有计算节点需要安装相同的操作系统，网卡的设备名称需统一，例如统一指定为enp0s0。

8. Mevoco系统在Mevoco 1.4之前使用Java 1.7版本，从Mevoco 1.6以后开始使用Java 1.8版本。

* 安装最新的Mevoco前，用户没有安装Java， Mevoco会默认安装1.8版本。

* 如果用户已安装其他版本，可单独安装Java 1.8版本，并通过update-alternatives --config java命令选择Java版本为1.8，配置后可通过java –version命令查看Java版本。若设置成其他版本，在后续部署与使用过程中可能导致异常。

* 如果用户从低版本升级到Mevoco最新版本，则Mevoco会默认自动升级Java到Java 1.8版本。

9. 浏览器：推荐使用最新版Chrome或Firefox浏览器访问Mevoco图形界面。建议浏览器的窗口宽度应该大于1280，宽度过小可能会影响使用效果。


