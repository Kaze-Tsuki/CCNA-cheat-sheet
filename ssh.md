# SSH

Enable ssh connection for a switch.

## Set IP

```bash
# config
interface vlan 1
ip address [ip] [netmask]
no shutdown
```

## SSH Settings

- hostname / domain name
```bash
# config
hostname [Switch-Name]
ip domain-name [Domain-Name]
```

- RSA key
```bash
# config
crypto key generate rsa
```

- SSH version
```bash
# config
ip ssh version 2
```

## Local User

- Create User
```bash
# config
username [Username] privilege 15 secret [Password]
```

- VTY
```bash
# config
line vty 0 15
login local
transport input ssh
```

## Enable Password

```bash
# config
enable secret [Password]
```
