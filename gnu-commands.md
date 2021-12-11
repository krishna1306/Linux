#### Run a command in background 

`nohup` -> No hang up

```
nohup command-with-options &
```

##### Print the system uptime since last reboot

```bash
uptime
```

##### Force kill a program

```bash
kill -9 sample-pid
```

##### Check the type of a command

Two command types

1. Shell built-in
2. External (present somewhere in `/bin` or `/usr/bin` etc.,)

To find out the type of a command, use `type` tool

```bash
type command-name
```

##### `pushd` and `popd`

Use `pushd` to pop in a directory into the stack and then automatically `cd` into it

When you want to go to the previous working directory, you can simply do `popd`

This is better than `cd -` as it only remembers your previous working directory.

`pushd` / `popd` doesn't care how many times you did `cd` in between. It just pops the pushed directories using `pushd` command.

**Example**

```bash
[~] pushd India
[~/India] cd Mumbai
[~/India/Mumbai] cd Bandra
[~/India/Mumbai/Bandra] popd
[~]
```

##### `ls` with options

**`ls -ltr`** -> Latest files first

**`ls -lt`** -> Oldest files first

#### Help

```bash
whatis
man
date --help

> apropos modpr
modprobe(8)
modeprobe.d(5)
```

##### Change Shell

```bash
chsh <path-to-new-shell>

chsh bob -s /bin/sh
# Asks for the password
```

##### Create Alias

```bash
alias dt=date
```

##### See history

```bash
history
```

##### Find out where a command is located

```bash
which obs-studio
```

##### Change the path - add a new path to the list

```bash
export PATH=$PATH:/opt/obs/bin
```

##### Check open ports

```bash
netstat -an | grep 5432
```

