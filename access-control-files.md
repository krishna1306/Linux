`/etc/passwd`

Contains UID, GID, Home Directory and Shell

```bash
# Syntax of each line
USERNAME:PASSWORD:UID:GID:GECOS:HOMEDIR:SHELL
```

`GECOS` - contains comments, phone numbers etc., Its _optional_

`/etc/shadow` contains passwords

```bash
# Syntax
USERNAME:PASSWORD:LASTCHANGE:MINAGE:MAXAGE:WARN:INACTIVE:EXPDATE
```

`/etc/group` contains group info

```bash
# Syntax
NAME:PASSWORD:GID:MEMBERS
```