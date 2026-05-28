# LACP

Use many physical links as one logical link

|channel mode|usage|
|-|-|
|desirable|Actice use *PAgP*|
|auto|Passive use *PAgP*|
|active|Actice use *LACP*|
|passive|Passive use *LACP*|
|on| Eth channel only|

```bash
int [interface]
channel-group [channel-id] mode [channel-mode]
```

```bash
int port-channel [id]
# other setup on interface
```