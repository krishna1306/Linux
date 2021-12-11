**See the current shell**

```bash
$SHELL
```

**Home Directory of current user**

```bash
$HOME
```

#### See all environment variables

```bash
env
```

##### Export a new variable

```bash
export OFFICE=caleston
```

Add the variables to `~/.profile` to make them persistent (Or `~/.pam_environment`) in the user's home directory

##### Check the user

```bash
$LOGNAME
```

##### Search for commands through `path`

```bash
$PATH
```

#### Bash prompt is set using 

```bash
$PS1
[\W]$
```

`\W` -> present working directory

```bash
PS1="[\d \t \u@\h:\w ] $ "
```

`\d` -> date

`\t` -> time

`\u` -> username

`\h` -> hostname

`\w` -> current working directory