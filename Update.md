# Firmware Update
```
ubnt-systool fwupdate /tmp/fw.bin
```

# Network Application
```
apt-get install -y /tmp/unifi-uos_sysvinit.deb
```

# Fix broken package
```
dpkg --remove --force-all unifi-native
```


# Documentation
[UniFi - Advanced Updating Techniques](https://help.ui.com/hc/en-us/articles/204910064-UniFi-Advanced-Updating-Techniques)
