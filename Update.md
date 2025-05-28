# Upload Firmware
```
scp \Download\fw.bin root@192.168.1.1:/tmp
```

# Firmware Update
```
ubnt-systool fwupdate /tmp/fw.bin
```

# Network Application
### UDM Pro, UDM SE, UDM Max
```
apt-get install -y /tmp/unifi-uos_sysvinit.deb
```

###  UDM, UDR, UDR7, Express, Express 7, UCG-Ultra, UCG-Max, and UCG-Fiber
```
apt-get install -y /tmp/unifi-native_sysvinit.deb
```

# Fix broken package
```
dpkg --remove --force-all unifi-native
```


# Documentation
[UniFi - Advanced Updating Techniques](https://help.ui.com/hc/en-us/articles/204910064-UniFi-Advanced-Updating-Techniques)
