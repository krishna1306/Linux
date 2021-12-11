`/root` -> Root's home

`/home` -> Home to home directories of all users

`/opt` -> Third party programs

`/mnt` -> Temporary FS Mounting area

`/tmp` -> Stores temporary data

`/media` -> All external media is mounted here (like USB)

```bash
# Shows information about all mounted file systems
df -hP
```

`/dev` -> Contains block and character devices

(USB mount under `/mount` will ultimately point to one of the block files under `/dev`)

`/bin` -> Basic GNU tools

`/etc` -> Most config files are present here

`/lib` and `/lib64` -> Shared libraries that can be imported into programs

`/usr` -> All user land applications and their data go here (Example - `vi` `mozilla`)

`/var` -> All logs are logged into this directory under `/var/logs` mostly)