### Variables

```bash
mission_name=lunar-mission
mkdir $mission_name
```

A variable name may only contain alpha-numeric and underscores.

A variable can also store the output of a command

```bash
rocket_status=$(rocket-status $mission_name)
```

Here `$()` will run the command in the curved paranthesis and then assigns the result to `rocket_status`

##### String Concatenation

```bash
new_variable=$old_variable"_something_new"
```

### Command Line Arguments

First argument of the any command can be accessed at `S1`

Command itself is available at `S0` 

```bash
mission_name=$1
```

### Read Inputs

```bash
read -p "Enter the mission name: " mission_name
```

Whatever is entered by the user will be assigned to `$mission_name`

### Immediately Exit if there is an issue

```bash
set -e
```

This makes sure the script exits if any command has a non-zero exit status

### Arithmatic Operations

```bash
expr 3 + 6
```

`expr` can be used for arithmatic expressions.

Operator `+` and values must be strictly separated by space

```bash
expr 6 \* 3
```

`*` must be escaped as it is a special character in `bash`

#### Double Paranthesis way

```bash
echo $(( A + B ))
```

Use `$(())` to do arithmatic operations

Here `A` and `B` can be variables too. No need to do `$A` + `$B`

**Floating point** is not supported in arithmatic operation

#### Bash Calculator - `bc`

```bash
echo $(( 10 / 3 )) | bc -l
3.3333
```

`bc` can also work as a standalone calculator

### Running a command in bash

Two ways

```bash
VAR=`echo $PATH`
```

```bash
VAR=$(echo $PATH)
```

### Conditional Logic

```bash
if [$rocket_status = "failed"]
then
	rocket-debug $mission_name
fi
```

```bash
if [$rocket_status = "failed"]
then
	rocket-debug $mission_name
elif [$rocket_status = "success"]
then
	echo "It is successful"
fi
```

```bash
if [$rocket_status = "failed"]
then
	rocket-debug $mission_name
elif [$rocket_status = "success"]
then
	echo "It is successful"
else
	echo "The state is not failed or success"
fi
```

#### Comparison statements

```bash
[ STRING1 = STRING2 ]

#or for bash and other modern shells

[[ STRING1 = STRING2 ]]
```

Spaces are **very important**

#### Comparison Operators

| Operator                 | Used For |
| ------------------------ | -------- |
| `[ string1 = string2 ]`  | String   |
| `[ string1 != string2 ]` | String   |
| `[ num1 -eq num2 ]`      | Number   |
| `[ num1 -ne num2 ]`      | Number   |
| `[ num1 -gt num2 ]`      | Number   |
| `[ num1 -lt num2 ]`      | Number   |

#### Double Bracket Special Use-cases `[]`

```bash
[[ "abc" = *b* ]]

[[ "abc" = ab[cd] ]]

[[ "abc" > "bca" ]]

[[ "bcd" < "ade" ]]
```

Pattern matching (similar to that of basic regex) can be done within `[[ ]]`

#### Conditional Operator

```bash
## SINGLE BRACKET
#and
[ condition1 ] && [ condition2 ]
#or
[ condition1 ] || [ condition2 ]

## DOUBLE BRACKET
#and
[[ condition1 && condition2 ]]
#or
[[ condition1 || condition2 ]]

```

#### File Checks

| Command       | Description                          |
| ------------- | ------------------------------------ |
| `[ -e FILE ]` | File exists                          |
| `[ -d FILE ]` | File exists and is a **directory**   |
| `[ -x FILE ]` | File exists and is an **executable** |
| `[ -s FILE ]` | File exists and **size > 0**         |
| `[ -w FILE ]` | File exists and is **writeable**     |

