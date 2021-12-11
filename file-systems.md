## Steps in adding a new disk

1. Create a partition
2. Create File System
3. Mount File System

### Create File System

```dev
mkfs.ext4 /dev/sdb1
```

See the type of filesystem

```bash
df -hP
blkid
```



### Mount it

```bash
mkdir /mnt/ext4

mount /dev/sdb1 /mnt/ext4
```

To verify

```bash
mount | grep /dev/sdb1

df -hP | grep /dev/sdb1
```

### Make a Mount Automatic at reboot

```bash
/dev/sda1	/	ext4	rw 0 0
```

```bash
# Syntax
DISK MOUNT-DIR FS-TYPE (rw|ro) DUMP FSCK
```

DUMP is a backup utility. `0` to disable

FSCK is the priority to check file system upon crash. `0` to ignore