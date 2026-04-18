# RIP Routing

## Diff of v1 v2

|Version|v1|v2|
|-|-|-|
|classful|Yes (only /24,/16,/8)|No|
|auto summary| No | Yes |
|VLSM| No | Yes |

## RIPv1

### Route Setup

```bash
# config
router rip
network [subnet]
```

### Default Route

```bash
# config
ip route 0.0.0.0 0.0.0.0 { ip-addr | exit-int }
router rip
default-information originate
```

### Passive Interface

- Method 1: make default
```bash
# config
router rip
passive-interface default
no passive-interface [interface]
```

- Method 2: Specify interfaced
```bash
# config
router rip
passive-interface [interface]
```

## RIPv2

### Change Version
```bash
# config
router rip
version 2
```

### Auto Summary
```bash
# config
router rip
no auto-summary
```

## Supplement

Not included in ccna's course, from [cisco](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/iproute_rip/configuration/xe-3e/irr-xe-3e-book/irr-ipsum-adr-rip2.html)

### With Subnet
Only in RIPv2
```bash
# config-if
ip summary-address rip [ip] [netmask]
```

### Split Horizon
Default enabled. Avoid learned route sent back, can be set most of the time, avoid loop. Do not open if using a hub-and-spoke topo.
```bash
# config-if
no ip split-horizon
```

### Recieve & Send Version

```bash
# config-if
ip rip send version 1 2    # send both v1 v2
ip rip receive version 2   # only recieve v2
```
