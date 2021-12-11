## Redirect

**Redirect is for files**

Three data streams

- `stdin` - Standard Input
- `stdout` - Standard Output
- `stderr` - Standard Error

#### `>` 

Send the output of one command to a file

```bash
echo $SHELL > shell.txt
```

#### `>>`

To append the contents of the file

```bash
echo $SHELL >> shell.txt
```

#### `2>` and `2>>`

```bash
cat missing_file 2> error.txt

# Appended
cat missing_file 2>> error.txt
```

#### Ignore `stderr`

```bash
cat missing_file 2> /dev/null
```

## Pipes

**Pipes are for processes**

Redirect as well as display on `stdout` by using `tee` command

```bash
echo $SHELL | tee shell.txt

# To append
echo $SHELL | tee -a shell.txt
```

