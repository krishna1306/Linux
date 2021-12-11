![lvm-funda](/Users/kribandi/Desktop/lvm-funda.png)

1. Group a bunch of physical disks or partitions and form a **Volume Group**
2. Create **Volumes** from this volume group - it's like a partition of the **Volume Group**
3. Create a File System on top of the **Volume**
4. Mount it wherever you like

Physical Volume ---> Volume Group ---> Logical Volume ---> File System ---> Mount

```bash
# Install LVM
apt-get install lvm2

# Create a physical volume - its like prepping up a disk or partition for LVM
pvcreate /dev/sdb

# Create a volume group. You can pass multiple disks as arguments here
vgcreate caleston_vg /dev/sdb

# See all the PVs created
pvdisplay

# See all the VGs created
vgdisplay

# Create a logical volume
# -L : Linear Volume - make use of multiple PVs underneath to allocate blocks
# -n : name
lvcreate -L 1G -n vol1 caleston_vg

# See all Logical Volumes
lvdisplay

# See all Logical Volumes - Summary
lvs

# Create a file system
mkfs.ext4 /dev/caleston_vg/vol1

# Mount the file system
# -t : Indicate the filesystem type (optional, but recommended)
mount -t ext4 /dev/caleston_vg/vol1 /mnt/vol1
```

```bash
vgs

lvresize -L +1G -n /dev/caleston_vg/vol1
```

**After resizing the logical volume, you need to resize the filesystem too**

```bash
# No need to unmount - to resize
resize2fs /dev/caleston_vg/vol1
```

