Linux can boot into multiple modes. For example

- Graphical mode
- CLI mode

These modes are called **run levels**

```bash
runlevel
# N 3 --> For CLI
# N 5 --> For GUI
```

In `systemd` **run levels** are called **targets**

| Run Level | Targets          | Function       |
| --------- | ---------------- | -------------- |
| 5         | graphical.target | Boots into GUI |
| 3         | multiuser.target | Boots into CLI |

**Check default run level**

```bash
systemctl get-default

# Or check the contents of the below file
ls -ltr /etc/systemd/system/default.target
# This is linked to /lib/systemd/system/graphical.target
```

**Change default target**

```bash
systemctl set-default multi-user.target
```

#### RUN LEVELS <-> TARGETS

**runlevel 0 -> poweroff.target**

**runlevel 1 -> rescue.target**

**runlevel 2 -> multi-user.target**

**runlevel 3 -> multi-user.target**

**runlevel 4 -> multi-user.target**

**runlevel 5 -> graphical.target**

**runlevel 6 -> reboot.target**

## Using SYSTEMD to run programs

Create a service file at `/etc/systemd/system/project-mercury.service`

```bash
[Unit]
Description=Python Django for Project Mercury
Documentation=http://wiki.caleston-dev.ca/mercury

After=postgresql.service

[Service]
ExecStart= /bin/bash /usr/bin/project-mercury.sh
WorkingDirectory=/home/pi
User=project_mercury
Restart=on-failure
RestartSec=10

[Install]
WantedBy=graphical.target
```

```bash
systemctl start project-mercury.service
```

#### Run `daemon-reload` whenever service definition changes

```bash
systemctl daemon-reload
```

## Systemd Tools

### Systemctl

```bash
systemctl start docker
systemctl stop docker
systemctl restart docker

# restat without disruption - generally to reload config file if any
systemctl reload docker
systemctl enable docker
systemctl disable docker

systemctl status docker
```

#### To edit an existing `.service` file

```bash
systemctl edit project-mercury.service --full
```

#### To manage state

```bash
systemctl get-default
systemctl set-default multi-user.target

# Prints all units in all states attempted by systemd
systemctl list-units --all

# See only active units
systemctl list-units
```

### Journalctl

Query `journal` systemd service to fetch logs and other important events

```bash
# see all logs
journanctl 

# Logs captured starting from boot
journalctl -b

journalctl -u docker.service
```

