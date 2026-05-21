# FHRP

Settings for VRRP, HSRP.

## VRRP

```bash
# config
int vlan [vlan-id]
ip addr [ip] [netmask]
vrrp [group-id] priority [value]
vrrp [group-id] ip [virtual-ip]
```

- No preempt
```bash
# config-if
no vrrp [group-id] preempt
```

## HSRP

```bash
# config
int [interface]
standby version 2
standby [group-id] ip [vip]
```

- Preempt: Actively takeover when it has higher priority
```bash
standby [group-id] priority [value]
standby [group-id] preempt
```