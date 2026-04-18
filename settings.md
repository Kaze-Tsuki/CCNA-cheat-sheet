# Settings

## Help

To see the options of the command, use `?`

## Save

```bash
# enable
copy running-config startup-config
```

## Log Config

### SSH

- SSH and RSA key
```bash
# enable
show ip ssh
show crypto key mypubkey rsa
```

### Running Config
Overview

```bash
# enable
show running-config
```

## Interfaces

- All: list interfaces state
```bash
# enable
show interfaces [status/trunk]
```

- Specify Interface: show detail settings of the interface
```bash
# enable
show interfaces [int-type] [member/module/name] switchport
show interfaces fa 0/1 switchport
```

### Vlan

Check ports and vlan mapping

- All
```bash
# enable
show vlan
show vlan brief
```

- Specify Vlan
```bash
# enable
show vlan id [vlan-id]
```

### Spanning Tree

- All
```bash
# enable
show spanning-tree
show spanning-tree summary detail
```

- Specify Interface
```bash
# enable
show spanning-tree int [interface] detail
```

- Specify Vlan
```bash
# enable
show spanning-tree vlan [vlan-id]
```

- Inconsistent Port
```bash
# enable
show spanning-tree inconsistentports
```

### Route Check

- Route: show ip/LAN it can reach
```bash
# enable
show ip route
```

- ARP: show all MAC and ip in same VLAN
```bash
# enable
show arp
```

## Check MAC Address

- Device
```bash
ipconfig /all
```

- Switch
```bash
# enable
show mac-address-table # neighbor
show int [interface] # interface mac
```

- Router
```bash
# enable
show arp
```
