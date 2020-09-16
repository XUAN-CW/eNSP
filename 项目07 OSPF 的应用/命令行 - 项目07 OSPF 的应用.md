# 任务02 主机与交换机配置

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

### SW-5

```
system-view
undo info-center enable
sysname SW-5

vlan batch 19 20

interface Ethernet 0/0/1
port link-type access
port default vlan 19
quit
interface Ethernet 0/0/2
port link-type access
port default vlan 20
quit

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 19 20
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

vlan batch 21 22

interface Ethernet 0/0/1
port link-type access
port default vlan 21
quit
interface Ethernet 0/0/2
port link-type access
port default vlan 22
quit

interface GigabitEthernet 0/0/1
port link-type trunk
port trunk allow-pass vlan 21 22
quit

display vlan

quit
save
y


```

# 任务03 配置路由交换机实现 VLAN 间通信

### RS-1

```
system-view
undo info-center enable
sysname RS-1

vlan batch 11 12

interface GigabitEthernet 0/0/24
port link-type trunk
port trunk allow-pass vlan 11 12
quit

interface vlanif 11
ip address 192.168.64.254 255.255.255.0
quit

interface vlanif 12
ip address 192.168.65.254 255.255.255.0
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

vlan batch 13 14

interface GigabitEthernet 0/0/24
port link-type trunk
port trunk allow-pass vlan 13 14
quit

interface vlanif 13
ip address 192.168.66.254 255.255.255.0
quit

interface vlanif 14
ip address 192.168.67.254 255.255.255.0
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

vlan batch 15 16

interface GigabitEthernet 0/0/24
port link-type trunk
port trunk allow-pass vlan 15 16
quit

interface vlanif 15
ip address 192.168.68.254 255.255.255.0
quit

interface vlanif 16
ip address 192.168.69.254 255.255.255.0
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
sysname RS-1

vlan batch 17 18

interface GigabitEthernet 0/0/24
port link-type trunk
port trunk allow-pass vlan 17 18
quit

interface vlanif 17
ip address 192.168.70.254 255.255.255.0
quit

interface vlanif 18
ip address 192.168.71.254 255.255.255.0
quit

quit
save
y

display ip routing-table
display vlan

```

### RS-5

```
system-view
undo info-center enable
sysname RS-1

vlan batch 19 20

interface GigabitEthernet 0/0/24
port link-type trunk
port trunk allow-pass vlan 19 20
quit

interface vlanif 19
ip address 192.168.72.254 255.255.255.0
quit

interface vlanif 20
ip address 192.168.73.254 255.255.255.0
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
sysname RS-1

vlan batch 21 22

interface GigabitEthernet 0/0/24
port link-type trunk
port trunk allow-pass vlan 21 22
quit

interface vlanif 21
ip address 192.168.74.254 255.255.255.0
quit

interface vlanif 22
ip address 192.168.75.254 255.255.255.0
quit

quit
save
y

display ip routing-table
display vlan

```

### 测试连通性

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

```
ping 192.168.72.1
```

```
ping 192.168.73.1
```

```
ping 192.168.74.1
```

```
ping 192.168.75.1
```



# 















