

# 任务03 在 eNSP 中访问 VirtualBox 虚拟机

## 步骤3:在VirtualBox中创建CentOS 7虚拟机

### 网卡配置文件

1. 使用vi命令编辑网卡配置文件〔此处为ifcfg-enp0s3).配置主机的IP地址(192.168.64.20/24)

```
vi /etc/sysconfig/network-scripts/ifcfg-enp0s3
```

2. 将IP地址的获得方式改为静态

```
BOOTPROTO=static
```

3. 将“ONBOOT”的值改为“yes”，表示将配置修改为开机启动

```
ONBO0T=yes
```

4. 增加i该语句，用“IPADDR=””来配置静态IP地址

```
IPADDR=192.168.64.20
```

5. 增加该语句，用“NETMASK”来配置子网掩码

```
NETMASK=255.255.255.0
```

6.  增加该语句，用“GATEWAY=”来配置本机的默认网关

```
GATEWAY=192.168.64.1
```

7. 不知道为什么，我比视频里少了最后这一行，补上

```
DNS1=114.114.114.114
```

### ifcfg-enp0s3 最终内容

经过我的仔细观察，我这里仅 `UUID=6015306c-26c4-475d-8b9e-b94f0f62c97b` 跟视频上的不一样

```
TYPE=Ethernet
PROXY_METHOD=none
BROWSER_ONLY=no
BOOTPROTO=static
DEFROUTE=yes
IPV4_FAILURE_FATAL=no
IPV6INIT=yes
IPV6_AUTOCONF=yes
IPV6_DEFROUTE=yes
IPV6_FAILURE_FATAL=no
IPV6_ADDR_GEN_MODE=stable-privacy
HAME=enp0s3
UUID=6015306c-26c4-475d-8b9e-b94f0f62c97b
DEVICE=enp0s3
IPADDR=192.168.64.20
NETMASK=255.255.255.0
GATEWAY=192.168.64.1
ONBO0T=yes
DNS1=114.114.114.114
```

## 步骤4:测试Host-1与VirtualBox虚拟机通信情况

1. IP地址设置后，使用systemctl restart network重启网络服务，使刚才的配置改生效

```
systemctl restart network
```

2. 使用Ping命令测试Host-1 (192.168.64.10/24)和VirtualBox中的Centos7虚拟机(192.168.64.20/24)之间的通信

```
ping 192.168.64.10
```

