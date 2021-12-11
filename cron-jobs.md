```bash
# for user specific cronjobs
crontab -e
```

**_Do not use `sudo` with `crontab` command_**

#### Syntax

```bash
min hours days months weekday command
```

Example

```bash
10 8 19 2 *
```

8:10am 19th of each month irrespective of the weekday

```bash
10 * * * *
```

10th minute of every hour

```bash
*/2 * * * *
```

 Every 2 mins

#### List all jobs

```bash
crontab -l
```

You can also check in `/var/log/syslog`