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
# config
int [int-type] [int-num]
switchport trunk allowed vlan [somevlans]
switchport access vlan [vlan-id]
switchport mode [trunk/access]
```

## L3 Switch

### Create Vlan

Create a vlan
```bash
# config
vlan [number]
name [name] # optional
```

Set Vlan Interface (SVI) and gateway ip
```bash
# config
int vlan [vlan-id]
ip address [ip] [netmask]
```

After all, enable routing
```bash
# config
ip routing
```

### Interface

For trunk interfaces need encapsulation
```bash
# config
int [int-type] [int-num]
# setup encapsulation
switchport trunk encap dot1q
switchport trunk allowed vlan [somevlans]
switchport access vlan [vlan-id]
switchport mode [trunk/access]
```

## Disable Vlan(switchport)

```bash
# config-if
no switchport
ip addr [ip] [netmask]
```