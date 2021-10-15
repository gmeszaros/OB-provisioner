## start the edge dnsmasq service
```bash
dnsmasq -C /root/provision/dnsmasq.ob40.conf
```

## optionally start the edge http service
```bash
python3 -m http.server 3003 --directory ~/provision/www/ --bind $(ip -4 -o addr show up primary scope global |grep -o 'inet6\?\ [0-9a-f\.:]\+' | cut -f 2 -d ' ')
```
