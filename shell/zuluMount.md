# Mount/Unmount veracrypt volume using zuluMount cli

```shell
# Mount veracrypt volume /dev/sda in a mount point "hdd" of type vera
sudo zuluMount-cli -K 1000 -m -d /dev/sda -z hdd -t vera

# Unmount the volume
sudo zuluMount-cli -K 1000 -u -d /dev/sda 
```
