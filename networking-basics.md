```bash
# see all interfaces
ip link

# assign ip
ip addr add 192.168.1.1/24 dev eth0

# see route table
route
ip route

# add gateway
ip route add 192.168.2.0/24 via 192.168.1.1

# add default gateway
ip route add 0.0.0.0/0 via 192.168.1.1
ip route add default via 192.168.1.1
ip route add default dev eth0

# delete IP
ip addr del 192.168.1.1/24 dev eth0
```

```bash
ip link set dev eth0 up
ip link set dev eth0 down
```

