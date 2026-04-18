# Spanning Tree Protocol

## Portfast

Bypass listening and learning state

- On single interface
```bash
# config
int [interface]
spanning-tree portfast # disable to disable
```

- On all interface
```bash
# config
spanning-tree portfast default
```

## BPDU Guard

Avoid end device send malicious BPDU packets, on recieve enter **err-disabled state(down)**.

```bash
# config
int [interface]
spanning-tree bpduguard enable
```

## Root Guard

Avoid end device add an switch that has better superior BPDU, on recieve enter **root inconsistent state**.

```bash
# config
int [interface]
spanning-tree guard root
```

## Force Root

To force a switch as root, there are two ways.

```bash
# config
spanning-tree vlan [vlan-id] root {primary | secondary}
spanning-tree vlan [vlan-id] priority [value]
```

## Modify Cost

Modify the cost of a link can change its spanning tree topo. 
Lowest cost -> Root

```bash
# config
int [interface]
spanning-tree vlan [vlan-id] cost [cost]
```