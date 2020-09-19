# 任务02 主机与交换机配置

### SW-1

```
system-view
undo info-center enable
sysname SW-1

vlan batch 2 3

interface Ethernet 0/0/1
port link-type access
port default vlan 2
quit
interface Ethernet 0/0/2
port link-type access
port default vlan 3
quit

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 2 3
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

vlan batch 4 5

interface Ethernet 0/0/1
port link-type access
port default vlan 4
quit
interface Ethernet 0/0/2
port link-type access
port default vlan 5
quit

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 4 5
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

vlan batch 6 7

interface Ethernet 0/0/1
port link-type access
port default vlan 6
quit
interface Ethernet 0/0/2
port link-type access
port default vlan 7
quit

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 6 7
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

vlan batch 8 9

interface Ethernet 0/0/1
port link-type access
port default vlan 8
quit
interface Ethernet 0/0/2
port link-type access
port default vlan 9
quit

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 8 9
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

vlan batch 2 3 100

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 2 3
quit

interface GigabitEthernet 0/0/24
port link-type access
port trunk allow-pass vlan 100
quit

interface vlanif 2
ip address 172.16.64.254 255.255.255.0
quit

interface vlanif 3
ip address 172.16.65.254 255.255.255.0
quit

interface vlanif 100
ip address 10.0.1.1 255.255.255.0
quit

rip 1
version 2
network 10.0.0.0
network 172.16.0.0
quit

quit
save
y

display ip routing-table
display vlan

```

### RS-2

```
system-view
undo info-center enable
sysname RS-2

vlan batch 4 5 100

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 4 5
quit

interface GigabitEthernet 0/0/24
port link-type access
port trunk allow-pass vlan 100
quit

interface vlanif 4
ip address 172.16.66.254 255.255.255.0
quit

interface vlanif 5
ip address 172.16.67.254 255.255.255.0
quit

interface vlanif 100
ip address 10.0.2.1 255.255.255.0
quit

rip 1
version 2
network 10.0.0.0
network 172.16.0.0
quit

quit
save
y

display ip routing-table
display vlan

```

### RS-3

```
system-view
undo info-center enable
sysname RS-3

vlan batch 6 7 100

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 6 7
quit

interface GigabitEthernet 0/0/24
port link-type access
port trunk allow-pass vlan 100
quit

interface vlanif 6
ip address 172.16.68.254 255.255.255.0
quit

interface vlanif 7
ip address 172.16.69.254 255.255.255.0
quit

interface vlanif 100
ip address 10.0.3.1 255.255.255.0
quit

rip 1
version 2
network 10.0.0.0
network 172.16.0.0
quit

quit
save
y

display ip routing-table
display vlan

```

### RS-4

```
system-view
undo info-center enable
sysname RS-4

vlan batch 8 9 100

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 8 9
quit

interface GigabitEthernet 0/0/24
port link-type access
port trunk allow-pass vlan 100
quit

interface vlanif 8
ip address 172.16.70.254 255.255.255.0
quit

interface vlanif 9
ip address 172.16.71.254 255.255.255.0
quit

interface vlanif 100
ip address 10.0.4.1 255.255.255.0
quit

rip 1
version 2
network 10.0.0.0
network 172.16.0.0
quit

quit
save
y

display ip routing-table
display vlan

```

### R-1

```
system-view
undo info-center enable
sysname R-1

interface GigabitEthernet 0/0/0
ip address 10.0.0.1 255.255.255.252
quit
interface GigabitEthernet 0/0/1
ip address 10.0.1.2 255.255.255.252
quit
interface GigabitEthernet 0/0/2
ip address 10.0.2.2 255.255.255.252
quit
interface GigabitEthernet 0/0/3
ip address 10.0.0.10 255.255.255.252
quit

rip 1
version 2
network 10.0.0.0
quit

quit
save
y


display ip routing-table

```

### R-2

```
system-view
undo info-center enable
sysname R-2

interface GigabitEthernet 0/0/0
ip address 10.0.0.6 255.255.255.252
quit
interface GigabitEthernet 0/0/1
ip address 10.0.0.9 255.255.255.252
quit
interface GigabitEthernet 0/0/2
ip address 10.0.3.2 255.255.255.252
quit
interface GigabitEthernet 0/0/3
ip address 10.0.4.2 255.255.255.252
quit

rip 1
version 2
network 10.0.0.0
quit

quit
save
y


display ip routing-table

```

### R-3

```
system-view
undo info-center enable
sysname R-3

interface GigabitEthernet 0/0/0
ip address 10.0.0.2 255.255.255.252
quit
interface GigabitEthernet 0/0/1
ip address 10.0.0.5 255.255.255.252
quit
interface GigabitEthernet 0/0/3
ip address 100.1.1.1 255.255.255.252
quit

rip 1
version 2
network 10.0.0.0
quit

quit
save
y


display ip routing-table

```

# 任务03 配置自治系统 AS200 的内部网络

### SW-5

```
system-view
undo info-center enable
sysname SW-5

vlan batch 2 3

interface Ethernet 0/0/1
port link-type access
port default vlan 2
quit
interface Ethernet 0/0/2
port link-type access
port default vlan 3
quit

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 2 3
quit

display vlan

quit
save
y


```

### SW-6

```
system-view
undo info-center enable
sysname SW-6

vlan batch 4 5

interface Ethernet 0/0/1
port link-type access
port default vlan 4
quit
interface Ethernet 0/0/2
port link-type access
port default vlan 5
quit

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 4 5
quit

display vlan

quit
save
y


```

### SW-7

```
system-view
undo info-center enable
sysname SW-7

vlan batch 6 7

interface Ethernet 0/0/1
port link-type access
port default vlan 6
quit
interface Ethernet 0/0/2
port link-type access
port default vlan 7
quit

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 6 7
quit

display vlan

quit
save
y


```

### SW-8

```
system-view
undo info-center enable
sysname SW-8

vlan batch 8 9

interface Ethernet 0/0/1
port link-type access
port default vlan 8
quit
interface Ethernet 0/0/2
port link-type access
port default vlan 9
quit

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 8 9
quit

display vlan

quit
save
y


```

### SW-9

```
system-view
undo info-center enable
sysname SW-9

vlan batch 10 11

interface Ethernet 0/0/1
port link-type access
port default vlan 10
quit
interface Ethernet 0/0/2
port link-type access
port default vlan 11
quit

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 10 11
quit

display vlan

quit
save
y


```

### RS-5

```
system-view
undo info-center enable
sysname RS-5

vlan batch 2 3 100

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 2 3
quit

interface GigabitEthernet 0/0/24
port link-type access
port trunk allow-pass vlan 100
quit

interface vlanif 2
ip address 172.168.64.254 255.255.255.0
quit

interface vlanif 3
ip address 172.168.65.254 255.255.255.0
quit

interface vlanif 100
ip address 10.1.1.1 255.255.255.0
quit

ospf 1
area 1
network 10.1.1.0 0.0.0.3
network 192.168.64.0 0.0.0.255
network 192.168.65.0 0.0.0.255
quit
quit

quit
save
y

display ip routing-table
display vlan

```

### RS-6

```
system-view
undo info-center enable
sysname RS-6

vlan batch 4 5 100

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 4 5
quit

interface GigabitEthernet 0/0/24
port link-type access
port trunk allow-pass vlan 100
quit

interface vlanif 4
ip address 172.168.66.254 255.255.255.0
quit

interface vlanif 5
ip address 172.168.67.254 255.255.255.0
quit

interface vlanif 100
ip address 10.1.2.1 255.255.255.0
quit

ospf 1
area 1
network 10.1.2.0 0.0.0.3
network 192.168.66.0 0.0.0.255
network 192.168.67.0 0.0.0.255
quit
quit

quit
save
y

display ip routing-table
display vlan

```

### RS-7

```
system-view
undo info-center enable
sysname RS-7

vlan batch 6 7 100

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 6 7
quit

interface GigabitEthernet 0/0/24
port link-type access
port trunk allow-pass vlan 100
quit

interface vlanif 6
ip address 172.168.68.254 255.255.255.0
quit

interface vlanif 7
ip address 172.168.69.254 255.255.255.0
quit

interface vlanif 100
ip address 10.1.3.1 255.255.255.0
quit

ospf 1
area 1
network 10.1.3.0 0.0.0.3
network 192.168.68.0 0.0.0.255
network 192.168.69.0 0.0.0.255
quit
quit

quit
save
y

display ip routing-table
display vlan

```

### RS-8

```
system-view
undo info-center enable
sysname RS-8

vlan batch 8 9 100

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 8 9
quit

interface GigabitEthernet 0/0/24
port link-type access
port trunk allow-pass vlan 100
quit

interface vlanif 8
ip address 172.168.70.254 255.255.255.0
quit

interface vlanif 9
ip address 172.168.71.254 255.255.255.0
quit

interface vlanif 100
ip address 10.1.4.1 255.255.255.0
quit

ospf 1
area 1
network 10.1.4.0 0.0.0.3
network 192.168.70.0 0.0.0.255
network 192.168.71.0 0.0.0.255
quit
quit

quit
save
y

display ip routing-table
display vlan

```

### RS-9

```
system-view
undo info-center enable
sysname RS-8

vlan batch 10 11 100

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 10 11
quit

interface GigabitEthernet 0/0/24
port link-type access
port trunk allow-pass vlan 100
quit

interface vlanif 10
ip address 172.168.72.254 255.255.255.0
quit

interface vlanif 11
ip address 172.168.73.254 255.255.255.0
quit

interface vlanif 100
ip address 10.1.5.1 255.255.255.0
quit

ospf 1
area 1
network 10.1.5.0 0.0.0.3
network 192.168.72.0 0.0.0.255
network 192.168.73.0 0.0.0.255
quit
quit

quit
save
y

display ip routing-table
display vlan

```

### R-4

```
system-view
undo info-center enable
sysname R-4

interface Ethernet 0/0/0
ip address 10.1.0.1 255.255.255.252
quit
interface Ethernet 0/0/1
ip address 10.1.0.18 255.255.255.252
quit
interface GigabitEthernet 0/0/0
ip address 10.1.0.10 255.255.255.252
quit
interface GigabitEthernet 0/0/3
ip address 100.1.1.2 255.255.255.252
quit

ospf 1
area 0
network 10.1.0.0 0.0.0.3
network 10.1.0.8 0.0.0.3
network 10.1.0.16 0.0.0.3
quit
quit

quit
save
y


display ip routing-table

```

### R-5

```
system-view
undo info-center enable
sysname R-4

interface Ethernet 0/0/0
ip address 10.1.0.2 255.255.255.252
quit
interface Ethernet 0/0/1
ip address 10.1.0.5 255.255.255.252
quit
interface GigabitEthernet 0/0/1
ip address 10.1.1.2 255.255.255.252
quit
interface GigabitEthernet 0/0/2
ip address 10.1.2.2 255.255.255.252
quit

ospf 1
area 0
network 10.1.0.0 0.0.0.3
network 10.1.0.4 0.0.0.3
quit

area 1
network 10.1.1.0 0.0.0.3
network 10.1.2.0 0.0.0.3
quit

quit

quit
save
y


display ip routing-table

```

### R-6

```
system-view
undo info-center enable
sysname R-4

interface Ethernet 0/0/0
ip address 10.1.0.13 255.255.255.252
quit
interface Ethernet 0/0/1
ip address 10.1.0.6 255.255.255.252
quit
interface GigabitEthernet 0/0/0
ip address 10.1.0.9 255.255.255.252
quit
interface GigabitEthernet 0/0/3
ip address 10.1.3.2 255.255.255.252
quit

ospf 1
area 0
network 10.1.0.4 0.0.0.3
network 10.1.0.8 0.0.0.3
network 10.1.0.12 0.0.0.3
quit
area 2
network 10.1.3.0 0.0.0.3
quit

quit
save
y


display ip routing-table

```

### R-7

```
system-view
undo info-center enable
sysname R-7

interface Ethernet 0/0/0
ip address 10.1.0.14 255.255.255.252
quit
interface Ethernet 0/0/1
ip address 10.1.0.17 255.255.255.252
quit
interface GigabitEthernet 0/0/1
ip address 10.1.4.2 255.255.255.252
quit
interface GigabitEthernet 0/0/2
ip address 10.1.5.2 255.255.255.252
quit

ospf 1
area 0
network 10.1.0.12 0.0.0.3
network 10.1.0.16 0.0.0.3
quit
area 3
network 10.1.1.4 0.0.0.3
network 10.1.1.5 0.0.0.3
quit
quit

quit
save
y


display ip routing-table

```

# 任务04 通过 BGP 实现自治系统之间的通信

### R-3

```
display ip routing-table
```

### R-4

```
display ip routing-table
```

### R-3

```
bgp 100
peer 100.1.1.2 as-number 200
ipv4-family unicast
import-route rip 1
quit
quit

rip 1
import-route bgp
quit
quit

quit
save
y


```

### R-4

```
bgp 100
peer 100.1.1.1 as-number 200
ipv4-family unicast
import-route ospf 1
quit
quit

ospf 1
import-route bgp
quit
quit

quit
save
y


```

### R-3

```
display ip routing-table
```

### R-4

```
display ip routing-table
```

# 任务05 对 BGP 发布的路由信息进行过滤

### R-3

```
ip ip-prefix prefix-r3 index 10 deny 10.0.0.0 16 greater-equal 16 less-equal 32
ip ip-prefix prefix-r3 index 12 permit 0.0.0.0 less-equal 32
bgp 100
filter-policy ip-prefix prefix-r3 export
```

### R-4

```
display ip routing-table
```

### R-4

```
ip ip-prefix prefix-r4 index 10 deny 10.1.0.0 16 greater-equal 16 less-equal 32
ip ip-prefix prefix-r4 index 12 permit 0.0.0.0 less-equal 32
bgp 200
filter-policy ip-prefix prefix-r4 export
```

### R-3

```
display ip routing-table
```

# 任务06 配置 BGP 路由聚合

### R-3

```
system-view
bgp 100
ipv4-family unicast
aggregate 172.16.64.0 21 detail-suppressed
quit
quit

quit
save
y



```

### R-4

```
system-view
bgp 200
ipv4-family unicast
aggregate 172.168.64.0 21 detail-suppressed
aggregate 172.168.72.0 23 detail-suppressed
quit
quit

quit
save
y



```

### R-3

```
display ip routing-table
```

### R-4

```
display ip routing-table
```

# 任务07 抓包分析 BGP 更新路由的方式

### R-3

```
system-view
bgp 100
ipv4-family unicast
undo aggregate 172.16.64.0 21 detail-suppressed
quit
quit

quit
save
y



```













































































































































































































































