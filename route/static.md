# Static Route

## Configure

- Method 1: set by exit interface
```bash
# config
ip route [address] [netmask] [exit-int]
```

- Method 2: set by forward destination address
```bash
# config
ip route [address] [netmask] [exit-addr]
```