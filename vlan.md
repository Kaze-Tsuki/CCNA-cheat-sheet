# Vlan

vlan number range: 1-1005 normal, 1006-4094 extended

## Switch

### Create Vlan

```bash
switch(config)\# vlan [number]
switch(config-vlan)\# name [name] # optional
```

### Interface

Setup interfaces mode to vlans, trunk for multiple, access for one

```bash
switch(config)\# int [int-type] [int-num]
switch(config-if)\# switchport trunk vlan [some vlans]
switch(config-if)\# switchport access vlan [vlan-id]
switch(config-if)\# switchport mode [trunk/access]
```

## L3 Switch

### Create Vlan

Create a vlan
```bash
L3switch(config)\# vlan [number]
L3switch(config-vlan)\# name [name] # optional
```

Set Vlan Interface (SVI) and gateway ip
```bash
L3switch(config)\# int vlan [vlan-id]
L3switch(config-vlan)\# ip address [ip] [netmask]
```

After all, enable routing
```bash
L3switch(config)\# ip routing
```

### Interface

For trunk interfaces need encapsulation
```bash
L3switch(config)\# int [int-type] [int-num]
# setup encapsulation
L3switch(config-if)\# switchport trunk encap dot1q
L3switch(config-if)\# switchport trunk vlan [some vlans]
L3switch(config-if)\# switchport access vlan [vlan-id]
L3switch(config-if)\# switchport mode [trunk/access]
```
