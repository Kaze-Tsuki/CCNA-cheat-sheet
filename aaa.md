# AAA & ACL

## RADIUS Server (AAA)

### Router

- Setup RADIUS server
```bash
# config
aaa new-model
radius server [server-name]
address ipv4 [server-ip] {auth-port | server-port}
key [secret]
```

- Authentication method list
```bash
# config
aaa authentication login [list-name] [auth-list]
login authentication [list-name]
# Example
aaa authentication login ccna group radius local
line vty 0 15
login authentication ccna
```

### Switch (2960)

```bash
# config
aaa new-model
radius-server host [server-ip] key [secret]
# Auth is same as router
```

## ACL

### Standard

Filter by source ip only

```bash
ip access-list standard { number | Word } 
# rules execute up to down
deny [subnet] [netmask]
permit any
```

### Extended

By source, dst, dst port

```bash
ip access-list extended { number | Word } 
# rules execute up to down
deny { ip | tcp } [src_subnet] [src_netmask] [dst_subnet] [dst_netmask]
permit any
```

Example for port.
```bash
ip access-list extended { number | Word } 
# block all traffic to 80 port tcp
deny tcp any any eq 80
permit any
```

### Apply

```bash
int [interface]
ip access-list { num | Word } { in | out }
```