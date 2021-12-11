```bash
lsblk

ls -l /dev | grep "^b"
```

### See all partitions

```bash
fdisk

# To print the partitions
sudo fdisk -l /dev/sda
```

Disk label `gpt` 

### Partition Types

1. Primary 
2. Extended
3. Logical

#### Primary

Used to boot an operating system

4th primary partition can be used as extended partitions - up to 16 logical partitions inside extended partitions

### Partition Schemes

#### MBR - Master Boot Record

Max 2TB

Max 4 partitions

```bash
fdisk /dev/sdb
```

Use `?` for help

#### GPT - GUID partition table

Unlimited partitions

No disk size restrictions

```bash
gdisk /dev/sdb
```

Use `?` for help

#### 