# IPv6 on Dream Machine
### Configure the IPv6 Tunnel
```
ip tunnel add he-ipv6 mode sit remote <server ipv4 address> local <client ipv4 address> ttl 255
ip link set he-ipv6 up
ip addr add <client ipv6 address> dev he-ipv6
ip route add ::/0 dev he-ipv6
ip -f inet6 addr
```
### Test connectivity
```
ping 2600::
```
### Firewall
```
/usr/sbin/ip6tables -I UBIOS_INPUT_GEOIP_PRECHK 1 -i he-ipv6 -j UBIOS_IN_GEOIP
/usr/sbin/ip6tables -I UBIOS_INPUT_USER_HOOK 1 -i he-ipv6 -j UBIOS_WAN_LOCAL_USER
/usr/sbin/ip6tables -I UBIOS_FWD_IN_GEOIP_PRECHK 1 -i he-ipv6 -j UBIOS_IN_GEOIP
/usr/sbin/ip6tables -I UBIOS_FWD_OUT_GEOIP_PRECHK -o he-ipv6 -j UBIOS_OUT_GEOIP
/usr/sbin/ip6tables -I UBIOS_FORWARD_IN_USER 1 -i he-ipv6 -j UBIOS_WAN_IN_USER
/usr/sbin/ip6tables -I UBIOS_FORWARD_IN_USER 1 -i he-ipv6 -j UBIOS_WAN_PF_IN_USER
/usr/sbin/ip6tables -I UBIOS_FORWARD_OUT_USER 1 -o he-ipv6 -j UBIOS_WAN_OUT_USER
/usr/sbin/ip6tables -I UBIOS_FORWARD_OUT_USER 1 -o he-ipv6 -j UBIOS_WAN_PF_OUT_USER
```

# Documentation
https://gist.github.com/bgrewell/591b5ce8809f2bbf0b3999921cecef60

https://github.com/telnetdoogie/UDMP-ipv6/tree/main?tab=readme-ov-file
