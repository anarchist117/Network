# Firmware Update
```scp
scp .\Downloads\fw.bin root@192.168.1.1:/tmp/fw.bin
```
```ssh
ssh root@192.168.1.1
ubnt-systool fwupdate /tmp/fw.bin
```

# Network Application
```
apt-get install -y /tmp/unifi-uos_sysvinit.deb
```



# Documentation
[UniFi - Advanced Updating Techniques](https://help.ui.com/hc/en-us/articles/204910064-UniFi-Advanced-Updating-Techniques)
