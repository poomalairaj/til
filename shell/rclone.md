# Use rclone to create a cloud remote and a crypt remote and mount it as FUSE fs

```shell
rclone config

# select "n" for new remote
# Provide a name for the remote
# Select the serial number of the storage cloud you want to use
# enter API key
# No need for advanced configuration
# accept the configuration 

# Now setup crypto remote
# select "n" for new remote
# set the name. For ex. "crypt"
# select 10 for encrypt/Decrypt a remote
# Set Remote as remote:bucket For ex. YOUR_BASE_REMOTE_NAME:/backup
# Select the file name encryption. For ex. standard
# encrypt the directory name. For. ex. true select 1
# select y to select your own password
# input your password
# input your password salt
```

## Mount the rclone as FUSE mount
```shell
rclone mount crypt: ~/mnt/1file  --allow-non-empty --cache-db-purge --buffer-size 32M --use-mmap --cache-dir /tmp/rclone/ --dir-cache-time 72h --drive-chunk-size 16M  --timeout 1h  --vfs-cache-mode writes --vfs-read-chunk-size 128M --vfs-read-chunk-size-limit 1G
```
