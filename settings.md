# Settings

## Save

```bash
switch\# copy running-config startup-config
```

## Log Config

### SSH

- SSH and RSA key
```bash
switch\# show ip ssh
switch\# show crypto key mypubkey rsa
```

### Running Config
Overview

```bash
switch\# show running-config
```

## Interfaces

- All: list interfaces state
```bash
switch\# show interfaces [status/trunk]
```

- Specify Interface: show detail settings of the interface
```bash
switch\# show interfaces [int-type] [member/module/name] switchport
switch\# show interfaces fa 0/1 switchport
```

### Vlan

Check ports and vlan mapping

- All
```bash
switch\# show vlan
switch\# show vlan brief
```

- Specify Vlan
```bash
switch\# show vlan id [vlan-id]
```

### Spanning Tree

- All
```bash
switch\# show spanning-tree
switch\# show spanning-tree summary detail
```

- Specify Interface
```bash
switch\# show spanning-tree int [interface] detail
```

- Specify Vlan
```bash
switch\# show spanning-tree vlan [vlan-id]
```

- Inconsistent Port
```bash
switch\# show spanning-tree inconsistentports
```