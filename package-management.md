### Need for package manager

- To make sure the package is secure - check the signatures
- Querying options - better package management
- Group packages for comfort (eg. sofware development suite)
- Manage dependencies

## `.deb`

**Install `.deb` file**

```bash
dpkg -i gimp.deb
```

`apt` is a new front of `dpkg`

`apt-get` is a traditional front end of `dpkg`

### DPKG

```bash
# Install
dpkg -i telnet.deb

# Un-install
dpkg -r telnet.deb

# Find more info about the package. Similar to '-q' in rpm
dpkg -l telnet

# Status of the package
dpkg -s telnet

# Verify the pacakge. Similar to '-Vf' in rpm
dpkg -p <path-to-file>
```

### APT / APT-GET

Repos for APT are present at `/etc/apt/sources.list`

```bash
apt install gimp
apt-get install gimp

# update the package information from all repos
apt update

# upgrade all packages
apt upgrade

# Edit repos
apt edit-sources
```

```bash
# remove a package
apt remove telnet

# look for a package in a repo
apt search telnet

# See all available packages
apt list
```

## `.rpm`

`yum` is a front of `rpm`

`dnf` - A feature rich front of `rpm`

### Installing with RPM

```bash
rpm -ivh telnet.rpm
```

`-i` install

`-v` verbose

```bash
# To un-install
rpm -e telnet.rpm

# To upgrade
rpm -Uvh telnet.rpm

# Query for a package
rpm -q telnet.rpm

# Verify a package
rpm -Vf <path-to-file>
```

`rpm` database is stored at `/var/lib/rpm` 

- packages list
- versions etc.,

### YUM

#### Repositories

Repos are stored at `/etc/yum.repos.d`

Each repository has an extension `.repo`

```bash

```

#### Commands

```bash
yum install httpd

# See all repos in your system
yum repolist

# Look for a package that provides scp command
yum provides scp

# Search for a package
yum search scp

# display info about a package
yum info scp

# Remove a package
yum remove httpd

# Update a package
yum update telnet
```

```bash
# Update all packages. Both 'update' and 'upgrade' do similar job
# 'upgrade' is recommended
yum update
yum upgrade
```

