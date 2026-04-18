# Show Route Settings

## Show all Routes

show all the routes that the switch knows
- S: static
- R: RIP
- O: OSPF
- AD: lower -> trustworthy -> prefered
- Metric: lower -> lower cost -> prefered
```bash
# enable
show ip route
```

## Protocol

show using routing protocols

```bash
# enable
show ip protocols
```

## OSPF

### Neighbor

List the neighbors of the router and its info of ospf.

```bash
# enable
show ip ospf neighbor
```
- FULL: normal
- DR/BDR/DROTHER: main/backup/others

### Type1 LSA
```bash
#enable
show ip ospf [process-id] database router
```
- Link State ID, ADV Router: the router id of this router

### Type2 LSA
```bash
# enable
show ip ospf [process-id] database network
```
- Link State ID: address of DR (not router id)
- ADV Router: router id of DR
