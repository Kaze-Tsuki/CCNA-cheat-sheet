# OSPF Routing

## Remainder

- Every area needs to direct connect to area 0
- area 0 must not be fragmented
- loopback > biggest ip, biggest ip in an area is DR, second is BDR

## Clear

```bash
# enable
clear ip ospf process
```

## Reference Bandwidth

```bash
# config
router ospf [router-id]
auto-cost reference-bandwidth [Mbps]
```

## Setup OSPF

1. Set Loopback (uneccessary)
```bash
# config
int loopback 0
ip addr [ip] [netmask]
```

2. Set process
```bash
# config
router ospf [process-id]
# (optional) set router id
router-id [ip]
```

3. Set networks
    - Global Config
    ```bash
        # config
        router ospf [process-id]
        network [subnet] {netmask | wildcard} area [area-id]
    ```

    - Per-interface
    ```bash
        #config
        int [interface]
        ip ospf [process-id] area [area-id]
    ```

## DR Election

1. priority (bigger)
2. router id (bigger)
    1. specified (router-id ...)
    2. loopback
    3. Biggest of all interface ip

Change priority (0-255)
```bash
# config
int [interface]
ip ospf priority [priority]
```

## OSPF Cost

- Method 1: Bandwidth
```bash
# config
int [interface]
bandwidth [Kbps]
```

- Method 2: cost (recommended)
```bash
# config
int [interface]
ip ospf cost [cost]
```

## Default Route

```bash
# config
ip route 0.0.0.0 0.0.0.0 { exit-int | exit-ip }
router ospf [process-id]
default-informmation originate
```

## Passive Interface

[See RIP Setting](./rip.md#passive-interface)

## Virtual Link

Situation:  
Backbone <-- ABR1 --> Area 10 <-- ABR2 --> Area 20

On ABR1
```bash
# config
router ospf [process-id]
area 10 virtual-link [ABR2-id]
```
On ABR2
```bash
# config
router ospf [process-id]
area 10 virtual-link [ABR1-id]
```

## Stub Area Types

|Area|External Routes (Type 4/5)|Inter-Area Routes (Type 3)|Default Route (Type 3)|
|-|-|-|-|
|Normal Area|Yes|Yes|Yes|
|Stub Area|No|Yes|Yes|
|Totally Stub Area|No|No|Yes|
|NSSA|Yes (as type 7)|Yes|No|
|Totally NSSA|Yes(as type 7)|No|Yes|

### Stub Area

No external, remain same if single area.

```bash
#config
router ospf [pid]
area [area-id] stub
```

### Totally Stub
**Only on ABR**

No external and summary type 3 as a default route.

```bash
#config
router ospf [pid]
area [area-id] stub no-summary
```

### Not-So-Stub

Allow redistributing external AS.

```bash
#config
router ospf [pid]
area [area-id] nssa
```

### Totally NSSA

Change type 3 LSA to 1 default route.

```bash
#config
router ospf [pid]
area [area-id] nssa no-summary
```
