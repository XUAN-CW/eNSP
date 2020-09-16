# 任务02 配置主机与交换机

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

# 任务03 配置路由交换机并进行通信测试

### RS-1

```
system-view
undo info-center enable
sysname RS-1

vlan batch 11 12

interface vlanif 11
ip address 192.168.64.254 255.255.255.0
quit

interface vlanif 12
ip address 192.168.65.254 255.255.255.0
quit

interface GigabitEthernet 0/0/24
port link-type trunk
port trunk allow-pass vlan 11 12
quit

display ip routing-table

quit
save
y


```

### RS-2

```
system-view
undo info-center enable
sysname RS-2

vlan batch 13 14

interface vlanif 13
ip address 192.168.66.254 255.255.255.0
quit

interface vlanif 14
ip address 192.168.67.254 255.255.255.0
quit

interface GigabitEthernet 0/0/24
port link-type trunk
port trunk allow-pass vlan 13 14
quit

display ip routing-table

quit
save
y


```

### RS-3

```
system-view
undo info-center enable
sysname RS-3

vlan batch 15 16

interface vlanif 15
ip address 192.168.68.254 255.255.255.0
quit

interface vlanif 16
ip address 192.168.69.254 255.255.255.0
quit

interface GigabitEthernet 0/0/24
port link-type trunk
port trunk allow-pass vlan 15 16
quit

display ip routing-table

quit
save
y


```

### RS-4

```
system-view
undo info-center enable
sysname RS-4

vlan batch 17 18

interface vlanif 17
ip address 192.168.70.254 255.255.255.0
quit

interface vlanif 18
ip address 192.168.71.254 255.255.255.0
quit

interface GigabitEthernet 0/0/24
port link-type trunk
port trunk allow-pass vlan 17 18
quit

display ip routing-table

quit
save
y


```

### 测试 VLAN11 和 VLAN12 间的连通性

```
ping 192.168.64.1
```
```
ping 192.168.65.1
```
```
ping 192.168.66.1
```
```
ping 192.168.67.1
```
```
ping 192.168.68.1
```
```
ping 192.168.69.1
```
```
ping 192.168.70.1
```
```
ping 192.168.71.1
```

# 任务04 配置路由接口地址

### RS-1

```
vlan 100
quit
interface vlanif 100
ip address 10.0.1.2 30
quit

interface GigabitEthernet 0/0/1
port link-type access
port default vlan 100
quit

display ip routing-table

quit
save
y


```

### RS-2

```
vlan 100
quit
interface vlanif 100
ip address 10.0.2.2 30
quit

interface GigabitEthernet 0/0/1
port link-type access
port default vlan 100
quit

display ip routing-table

quit
save
y


```

### RS-3

```
vlan 100
quit
interface vlanif 100
ip address 10.0.3.2 30
quit

interface GigabitEthernet 0/0/1
port link-type access
port default vlan 100
quit

display ip routing-table

quit
save
y


```

### RS-4

```
vlan 100
quit
interface vlanif 100
ip address 10.0.4.2 30
quit

interface GigabitEthernet 0/0/1
port link-type access
port default vlan 100
quit

display ip routing-table

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
ip address 10.0.0.1 30
quit
interface GigabitEthernet 0/0/1
ip address 10.0.0.9 30
quit
interface GigabitEthernet 0/0/2
ip address 10.0.1.1 30
quit
interface GigabitEthernet 0/0/3
ip address 10.0.2.1 30
quit

display ip routing-table

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
ip address 10.0.0.2 30
quit
interface GigabitEthernet 0/0/1
ip address 10.0.0.6 30
quit

display ip routing-table

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
ip address 10.0.0.5 30
quit
interface GigabitEthernet 0/0/1
ip address 10.0.0.10 30
quit
interface GigabitEthernet 0/0/2
ip address 10.0.3.1 30
quit
interface GigabitEthernet 0/0/3
ip address 10.0.4.1 30
quit

display ip routing-table

quit
save
y


```

# 任务05 配置 RIP 并进行全网通信测试

### RS-1

```
rip 1

version 2

network 192.168.64.0
network 192.168.65.0
network 10.0.0.0

quit
quit
save
y


```

### RS-2

```
rip 1

version 2

network 192.168.66.0
network 192.168.67.0
network 10.0.0.0

quit
quit
save
y


```

### RS-3

```
rip 1

version 2

network 192.168.68.0
network 192.168.69.0
network 10.0.0.0

quit
quit
save
y


```

### RS-4

```
rip 1

version 2

network 192.168.70.0
network 192.168.71.0
network 10.0.0.0

quit
quit
save
y


```

### R-1

```
system-view

rip 1

version 2

network 10.0.0.0

quit
quit
save
y


```

### R-2

```
system-view

rip 1

version 2

network 10.0.0.0

quit
quit
save
y


```

### R-3

```
system-view

rip 1

version 2

network 10.0.0.0

quit
quit
save
y


```

# 任务06 抓包分析 RIP 协议工作过程

```
display ip routing-table

```

```
tracert 192.168.68.1
```

















































































