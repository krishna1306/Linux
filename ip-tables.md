# IP Tables

```bash
sudo apt install iptables

# List rules
sudo iptables -L
```

Three chains

1. `input`
2. `forward`
3. `output`

![chains-iptables](/Users/kribandi/Desktop/chains-iptables.png)

##### Add a rule to `INPUT` chain

```bash
iptables -A INPUT -p tcp -s 172.16.238.187 --dport 22 -j ACCEPT
```

`-d` --> destination IP address can also be used

**Default rule** --> Accept all incoming connections

To add a generic rule that drop all other IPs

```bash
iptables -A INPUT -p tcp --dport 22 -j DROP
```

_Every time a rule is added, it's added at the bottom_

##### Add a rule to `OUTPUT` chain

```bash
iptables -A OUTPUT -p tcp -d 172.16.238.11 --dport 5432 -j ACCEPT
```

#### Add a rule at the top of the chain

```bash
iptables -I OUTPUT -p tcp 172.16.238.100 --dport 443 -j ACCEPT
```

##### Delete a rule

```bash
iptables -D OUTPUT 5 
```

Here `5` is the position of the rule we want to delete