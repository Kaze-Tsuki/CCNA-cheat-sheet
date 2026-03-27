# Spanning Tree Protocol

## Portfast

Bypass listening and learning state

- On single interface
```bash
switch(config)\# int [interface]
switch(config-if)\# spanning-tree portfast # disable to disable
```

- On all interface
```bash
switch(config)\# spanning-tree portfast default
```

## BPDU Guard

Avoid end device send malicious BPDU packets, on recieve enter **err-disabled state(down)**.

```bash
switch(config)\# int [interface]
switch(config-if)\# spanning-tree bpduguard enable
```

## Root Guard

Avoid end device add an switch that has better superior BPDU, on recieve enter **root inconsistent state**

```bash
switch(config)\# int [interface]
switch(config-if)\# spanning-tree guard root
```