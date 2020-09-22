# 任务01 实现园区网

### SW-1

```
system-view
undo info-center enable
sysname SW-1

vlan batch 11 12

interface Ethernet 0/0/1
port link-type access
port default vlan 11
quit
interface Ethernet 0/0/2
port link-type access
port default vlan 12
quit

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 11 12
quit

display vlan

quit
save
y


```

### SW-2

```
system-view
undo info-center enable
sysname SW-2

vlan batch 13 14

interface Ethernet 0/0/1
port link-type access
port default vlan 13
quit
interface Ethernet 0/0/2
port link-type access
port default vlan 14
quit

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 13 14
quit

display vlan

quit
save
y


```

### SW-3

```
system-view
undo info-center enable
sysname SW-3

vlan batch 15 16

interface Ethernet 0/0/1
port link-type access
port default vlan 15
quit
interface Ethernet 0/0/2
port link-type access
port default vlan 16
quit

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 15 16
quit

display vlan

quit
save
y


```

### SW-4

```
system-view
undo info-center enable
sysname SW-4

vlan batch 17 18

interface Ethernet 0/0/1
port link-type access
port default vlan 17
quit
interface Ethernet 0/0/2
port link-type access
port default vlan 18
quit

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 17 18
quit

display vlan

quit
save
y


```

### RS-1

```
system-view
undo info-center enable
sysname RS-1

vlan batch 11 12 100

interface vlanif 11
ip address 192.168.64.254 24
quit

interface vlanif 12
ip address 192.168.65.254 24
quit

interface vlanif 100
ip address 10.0.2.2 30
quit

interface GigabitEthernet 0/0/1
port link-type access
port trunk allow-pass vlan 100
quit

interface GigabitEthernet 0/0/24
port link-type trunk
port default vlan 11 12
quit

ospf 1
area 1
network 192.168.64.0 0.0.0.255
network 192.168.65.0 0.0.0.255
network 10.0.2.0 0.0.0.3
quit
quit

quit
save
y


```

### RS-2

```
system-view
undo info-center enable
sysname RS-2

vlan batch 13 14 100

interface vlanif 13
ip address 192.168.66.254 24
quit

interface vlanif 14
ip address 192.168.67.254 24
quit

interface vlanif 100
ip address 10.0.3.2 30
quit

interface GigabitEthernet 0/0/1
port link-type access
port trunk allow-pass vlan 100
quit

interface GigabitEthernet 0/0/24
port link-type trunk
port default vlan 13 14
quit

ospf 1
area 1
network 192.168.66.0 0.0.0.255
network 192.168.67.0 0.0.0.255
network 10.0.3.0 0.0.0.3
quit
quit

quit
save
y


```

### RS-3

```
system-view
undo info-center enable
sysname RS-3

vlan batch 15 16 100

interface vlanif 15
ip address 192.168.68.254 24
quit

interface vlanif 16
ip address 192.168.69.254 24
quit

interface vlanif 100
ip address 10.0.4.2 30
quit

interface GigabitEthernet 0/0/1
port link-type access
port trunk allow-pass vlan 100
quit

interface GigabitEthernet 0/0/24
port link-type trunk
port default vlan 15 16
quit

ospf 1
area 2
network 192.168.68.0 0.0.0.255
network 192.168.69.0 0.0.0.255
network 10.0.4.0 0.0.0.3
quit
quit

quit
save
y


```

### RS-4

```
system-view
undo info-center enable
sysname RS-4

vlan batch 17 18 100

interface vlanif 17
ip address 192.168.70.254 24
quit

interface vlanif 18
ip address 192.168.71.254 24
quit

interface vlanif 100
ip address 10.0.5.2 30
quit

interface GigabitEthernet 0/0/1
port link-type access
port trunk allow-pass vlan 100
quit

interface GigabitEthernet 0/0/24
port link-type trunk
port default vlan 17 18
quit

ospf 1
area 2
network 192.168.70.0 0.0.0.255
network 192.168.71.0 0.0.0.255
network 10.0.5.0 0.0.0.3
quit
quit

quit
save
y


```

### RS-5

```
system-view
undo info-center enable
sysname RS-5

vlan 100
interface vlanif 100
ip address 10.0.1.2 30
quit
vlan 10
interface vlanif 10
ip address 192.168.100.254 24
quit

interface GigabitEthernet 0/0/24
port link-type access
port default vlan 10
quit
interface GigabitEthernet 0/0/1
port link-type access
port trunk allow-pass vlan 100
quit

ospf 1
area 3
network 10.0.1.0 0.0.0.3
network 192.168.100.0 0.0.0.255
quit
quit

quit
save
y


```

### R-1

```
system-view
undo info-center enable
sysname R-1

interface GigabitEthernet 0/0/0
ip address 10.0.1.1 30
quit
interface GigabitEthernet 0/0/1
ip address 10.0.0.1 30
quit
interface GigabitEthernet 0/0/2
ip address 10.0.0.5 0
quit

ospf 1
area 0
network 10.0.0.0 0.0.0.3
network 10.0.0.4 0.0.0.3
quit
area 3
network 10.0.1.0 0.0.0.3
quit
quit

quit
save
y


```

### R-2

```
system-view
undo info-center enable
sysname R-2

interface GigabitEthernet 0/0/0
ip address 10.0.0.9 30
quit
interface GigabitEthernet 0/0/1
ip address 10.0.0.2 30
quit
interface GigabitEthernet 0/0/2
ip address 10.0.2.1 0
quit
interface GigabitEthernet 0/0/3
ip address 10.0.3.1 0
quit

ospf 1
area 0
network 10.0.0.0 0.0.0.3
network 10.0.0.8 0.0.0.3
quit
area 1
network 10.0.2.0 0.0.0.3
network 10.0.3.0 0.0.0.3
quit

quit
quit
save
y


```

### R-3

```
system-view
undo info-center enable
sysname R-3

interface GigabitEthernet 0/0/0
ip address 10.0.0.10 30
quit
interface GigabitEthernet 0/0/1
ip address 10.0.4.1 30
quit
interface GigabitEthernet 0/0/2
ip address 10.0.0.6 0
quit
interface GigabitEthernet 0/0/3
ip address 10.0.5.1 0
quit

ospf 1
area 0
network 10.0.0.4 0.0.0.3
network 10.0.0.8 0.0.0.3
quit
area 3
network 10.0.4.0 0.0.0.3
network 10.0.5.0 0.0.0.3
quit

quit
quit
save
y


```

# 任务02 部署 DHCP 服务器

```
vi /etc/sysconfig/network-scripts/ifcfg-enp0s3
```

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
UUID=bec9c070-c19f-49e4-aedd-bda667a8611a
DEVICE=enp0s3
IPADDR=192.168.100.200
NETMASK=255.255.255.0
GATEWAY=192.168.100.255
ONBO0T=yes
```

```
systemctl restart network
```

```
vi /etc/dhcp/dhcpd.conf
```

```
default-lease-time 600;
max-lease-time 7200;
subnet 192.168.100.0 network 255.255.255.0{
    range 192.168.100.10 192.168.100.20;
    option routers 192.168.100.254;
}
subnet 192.168.64.0 network 255.255.255.0{
    range 192.168.64.10 192.168.64.20;
    option routers 192.168.64.254;
}
subnet 192.168.65.0 network 255.255.255.0{
    range 192.168.65.10 192.168.65.20;
    option routers 192.168.65.254;
}
subnet 192.168.66.0 network 255.255.255.0{
    range 192.168.66.10 192.168.66.20;
    option routers 192.168.66.254;
}
subnet 192.168.67.0 network 255.255.255.0{
    range 192.168.67.10 192.168.67.20;
    option routers 192.168.67.254;
}
subnet 192.168.68.0 network 255.255.255.0{
    range 192.168.68.10 192.168.68.20;
    option routers 192.168.68.254;
}
subnet 192.168.69.0 network 255.255.255.0{
    range 192.168.69.10 192.168.69.20;
    option routers 192.168.69.254;
}
subnet 192.168.70.0 network 255.255.255.0{
    range 192.168.70.10 192.168.70.20;
    option routers 192.168.70.254;
}
subnet 192.168.71.0 network 255.255.255.0{
    range 192.168.71.10 192.168.71.20;
    option routers 192.168.71.254;
}
```

# 任务03 在园区网中实现 DHCP 服务

### RS-1

```
system-view

dhcp enable

interface vlanif 11
dhcp select relay
dhcp relay server-ip 192.168.100.200
quit
interface vlanif 12
dhcp select relay
dhcp relay server-ip 192.168.100.200
quit

quit
save
y


```

### RS-2

```
system-view

dhcp enable

interface vlanif 13
dhcp select relay
dhcp relay server-ip 192.168.100.200
quit
interface vlanif 14
dhcp select relay
dhcp relay server-ip 192.168.100.200
quit

quit
save
y


```

### RS-3

```
system-view

dhcp enable

interface vlanif 15
dhcp select relay
dhcp relay server-ip 192.168.100.200
quit
interface vlanif 16
dhcp select relay
dhcp relay server-ip 192.168.100.200
quit

quit
save
y


```

### RS-4

```
system-view

dhcp enable

interface vlanif 17
dhcp select relay
dhcp relay server-ip 192.168.100.200
quit
interface vlanif 18
dhcp select relay
dhcp relay server-ip 192.168.100.200
quit

quit
save
y


```

# 任务04 管理 DHCP 服务器

### 查看已分配 IP 地址信息

```
vi /var/lib/dhcpd/dhcpd.leases
```

### 为主机 Host-3 分配固定 IP 地址

```
vi /etc/dhcp/dhcpd.conf
```

```
host fantasia{
    hardware ethernet 54:89:98:1C:0F:54;
    fixed-address 192.168.66.19;
}
```

```
systemctl restart dhcpd
```

### 更多配置

```
subnet 192.168.100.0 network 255.255.255.0{
    range 192.168.100.10 192.168.100.20;
    option routers 192.168.100.254;
    option broadcast-address 192.168.64.255;
}
```

```
option domain-name "test.com";
```

```
option domain-name-servers 8.8.8.8;
```

```
option host-name Host-1;
```

```
option ntp-servers time.windows.com;
```













































































































































































































































































































































