# SSH

Enable ssh connection for a switch.

## Set IP

```bash
Switch(config)\# interface vlan 1
Switch(config-if)\# ip address [ip] [netmask]
Switch(config-if)\# no shutdown
Switch(config-if)\# exit
```

## SSH Settings

- hostname / domain name
```bash
Switch(config)\# hostname [Switch-Name]
Switch(config)\# ip domain-name [Domain-Name]
```

- RSA key
```bash
Switch(config)\# crypto key generate rsa
```

- SSH version
```bash
Switch(config)\# ip ssh version 2
```

## Local User

- Create User
```bash
Switch(config)\# username [Username] privilege 15 secret [Password]
```

- VTY
```bash
Switch(config)\# line vty 0 15
Switch(config-line)\# login local
Switch(config-line)\# transport input ssh
Switch(config-line)\# exit
```

## Enable Password

```bash
Switch(config)\# enable secret [Password]
```
