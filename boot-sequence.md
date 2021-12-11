### Boot Sequence

![boot-sequence](/Users/kribandi/Desktop/boot-sequence.png)

#### **POST** - Power ON Self Test

To check if the hardware components attached are functioning correctly

#### **Boot Loader**

Located in `/boot` file system.

Example - **Grub2**

Here, kernel is loaded into the memory and control handed over to the kernel

#### Kernel Initialisation

Kernel uncompressed

Initialize hardware. Sets up memory.

Starts the `init` process that kick starts user space applications/processes.

#### INIT Process

`init` calls `systemd` -> which then brings the system up into a usable state (example - setting up networks, mounting files etc.,)

`systemd` runs processes in parallel - unlike `sysv`

**Check if `systemd` is the init process**

```bash
ls -l /sbin/init
```

If `systemd` is in use, you will see a link to `/lib/systemd/systemd`