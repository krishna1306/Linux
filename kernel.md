Kernel is responsible for

- Memory management
- Process Management
- Device Drivers
- System Calls and Security

**Linux Kernel is monolithic and modular**

**Modular** -> Functionality can be extended through modules

```bash
# Which kernel is in use
uname

# Kernel version
uname -r
```

kernel.org -> Kernel source code.

### Memory Management

**Two areas**

1. Kernel space
   1. Device Drivers
2. User space
   1. Applications / Programs

### Working with Hardware

![working-with-hardware-1](/Users/kribandi/Desktop/working-with-hardware-1.png)

Check `dmesg` (kernel ring buffer) to see all messages related to detecting hardware (in addition to other things that a kernel does)

```bash
dmesg
```

#### Working with `udev` daemon

```bash
udevadm info --query=path --name=/dev/sda5
# Outputs the device path
```

```bash
# Monitor all the events sent by the device drivers in the kernel and also the 
# corresponding device files created by udev daemon
udevadm monitor
```

**List PCI**

```bash
# ethernet cards, raid cards etc.,
lspci
```

**List Block Devices**

```bash
lsblk
```

In the output, you will see `MAJ` and `MIN` 

Eg. `8:0`

Here, 8 refers to `SCSI` disk and 0 refers to the "main disk"

If it is `8:1` -> 1 refers to the 1st partition

| Major Number | Device Type         |
| ------------ | ------------------- |
| 1            | RAM                 |
| 3            | HARD DISK or CD ROM |
| 6            | PARALLEL PRINTERS   |
| 8            | SCSI DISK           |

**CPU Architecture**

```bash
lscpu
```

**List available memory**

```bash
lsmem --summary

# Full data
lsmem

# Total vs Free
free -m
```

**Get entire hardware configuration on the machine**

```bash
lshw
```



