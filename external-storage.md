3 Key types

1. DAS - Direct Attached Storage
2. NAS - Network Attached Storage
3. SAN - Storage Area Network

---

### DAS

Seen as directly attached block device.

### NAS

NFS is an example of NAS - where a file system is shared with a host instead of a block device (where you have to again partition and format it with a file system of your choice)

_NAS is **not recommended** for operating systems_

#### NFS

Works on a SERVER -- CLIENT model

A server shares a directory that can be mounted on any path on the client

Once mounted, it can be used like any other file system

#### On NFS Server

The file `/etc/exports` defines which clients can access the NFS server

```bash
/software/repos 10.16.35.201 10.61.35.202 10.61.35.203
```

Once configured, you can **export the shares**

```bash
# Export all shares in /etc/exports
exportfs -a

# Export only a specific share present in /etc/exports
exportfs -o 10.61.35.201:/software/repos
```

#### On the NFS Client

To mount the NFS share (this is only possible after the server is properly configured and exporting the share)

```bash
# mount <server-ip>:<share-path> <local-mount-path>
mount 10.61.112.101:/software/repos /mnt/software/repos
```

### SAN

Storage provided through fiber channels (FC, iSCSI)

Better performance for databases or Operating systems

Allocated through LUNs (Logical Unit Number)

A LUN is a series of blocks presented to the host as a logical disk