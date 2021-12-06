### Check for existence if input arguments

```bash
if [ $# -eq 0 ]
  then
    echo "No arguments supplied"
fi
```

```bash
if [ -z "$1" ]
  then
    echo "No argument supplied"
fi
```

`-z` checks if `$1` is an null or empty string. This also means there are no arguments

`$#` tells the total number of arguments passed.

#### Sleep

```bash
sleep 2
```

#### `break` and `continue`

`break` -> to break away from the loop

`continue` -> to continue to the beginning of the current loop

#### TRUE and FALSE booleans in `bash`

There is no boolean `TRUE` or `FALSE` in bash.

There is a `true` command that exits with `0` and 

there is a `false` command that exits with `1`

So, we can still use `true` or `false` as if they are booleans, but they are actually bash programs that returns a specific exit code

```bash
if true; then echo "yes"; fi
```

### Use SHEBANG

`shebang` instructs the computer to use a specifc shell

Always start with a `shebang`

```bash
#!/bin/bash
```

#### EXIT codes

EXIT STATUS **0** -- "SUCCESS"

EXIT STATUS **>0** -- "FAILURE"

Run `echo $?` to know the exit status of the previous command

```bash
echo $?
```

Always make sure to return approrpriate code

### Variables in BASH

All variables in bash are `global` in scope, by default - even if they are declared within a function

To declare a local variable that is only limited to that function

```bash
#!/bin/bash

function my_func(){
	global_var="variable1"
	local local_var="variable2"
}
```

### Utilities to identify issues in bash script

```bash
yum install shellcheck
```

Check the git repo

https://github.com/koalaman/shellcheck

##### Style-Guide

https://google.github.io/styleguide/shellguide.html

#### Write to a file in BASH

```bash
cat > somefile.txt <<-EOF
line1
line2
line3
EOF
```

