##### Defining a function

```bash
function launch_rocket() {
	arg1=$1
}
```

The first parameter passed to the function can be accessed through `$` inside the function

##### Calling the function

```bash
launch_rocket lunar_mission
```

*No braces are used when calling a function, unlike python or JS*

##### Return code in a function

`return` code is like an `exit` code for a function

```bash
MISSION_EXIT_CODE=$?
```

Just like we use `$?` to get an exit code for the command run last.

##### Getting values out of a function

```bash
function add() {
	echo $(( $1 + $2 ))
}

sum=$(add 3 2)

# Do not do this if possible
function add() {
	return $(( $1 + $2 ))
}

sum=$?
```

Here, `add` is treated as a command. So we need either `$( )` or back ticks to run the command

And the output is whatever echoed inside the function.