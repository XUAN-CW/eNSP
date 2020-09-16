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

































