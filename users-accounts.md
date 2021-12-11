## Accounts

Users file -> `/etc/passwd`

Groups file -> `/etc/groups`

### Users

```bash
# see user and group information
id micheal
```

Each user account has

- User name
- UID
- GID
- Home Directory
- Shell

#### Types of accounts

- Regular users (UID > 1000)
- Root
- System accounts (UID < 100 or 500 < UID < 1000) - Ex. MAIL, SSH
- Service accounts - Ex. NGINX, MERCURY

```bash
# Currently logged in users
who

# All users who logged in earlier
last
```

### SUDO Access

`/etc/sudoers` and `/etc/sudoers.d`

Or edit the config directly using `visudo` command

To allow `bob` user to have `root` privileges through `sudo` add the following line

```bash
bob ALL=(ALL:ALL) ALL

# For group
%sudo ALL=(ALL:ALL) ALL

# For allowing 'sarah' to just do shutdown
sarah localhost=/usr/bin/shutdown -r now
```

**Syntax**

```bash
USER HOST=(UID:GID) COMMAND
%GROUP HOST=(UID:GID) COMMAND
```

HOST -- `localhost` or `ALL`

(UID:GID) -- `(ALL:ALL)`

#### Disable login shell for `root`

Making sure that no one is allowed to login to a system as `root` is strongly recommended

```bash
grep -i ^root /etc/passwd
/root:x:0:0:root:/root:/usr/sbin/nologin
```

#### User Management

```bash
# Add user
useradd bob

# Set password
passwd bob

# Check self details
whoami

# delete
userdel bob
```

#### More options

```bash
useradd -u 1009 -g 1009 -d /home/robert -s /bin/bash -c "Mercury Project Member" bob
```

`-e` -> specify account expiration date

`-G` -> add secondary groups

#### Groups

```bash
groupadd -g 1011 developer

# delete
groupdel developer
```

