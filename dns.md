#### Local Resolution

`/etc/hosts`

This is the first file consulted for DNS resolution

#### DNS Server

If the DNS server IP is `192.168.1.100`, configure your host at `/etc/resolv.conf`

```bash
nameserver 192.168.1.100
```

In the DNS server, to forward all "unknown" requests to a specific name server, edit the `/etc/hosts` file with the line

```bash
Forward All to 8.8.8.8
```

#### Order of NS resolution

The order in which files are consulted for NS resolution is kept at `/etc/nsswitch.conf`

```bash
hosts: files dns
```

Meaning, `files` -> `/etc/hosts`

`dns` -> `/etc/resolv.conf`

#### Search Domain

In reality, your `/etc/hosts` may look like this

```bash
192.168.1.1 web.mycompany.com
192.168.1.2 www.mycompany.com
192.168.1.3 mail.mycompany.com
```

In order to resolve, you need to use full name `web.mycompany.com` to get `192.168.1.1` as the IP

To avoid typing full name, we use **search domains**

In `/etc/resolv.conf`

```bash
search company.com
```

#### Nameserver lookup Commands

```bash
nslookup www.google.com
# nslookup doesn't bother about /etc/hosts

dig www.google.com
# returns more details
```

#### Record Types

A -> IPv4

AAAA -> IPv6

CNAME -> Multiple names for a single domain (name to name mapping)