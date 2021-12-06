We can tell `echo` that we want to print strings in a specific color

```bash
echo -e "\e[32mRed text\e[0m"
```

`\e[COLORm` is the escape sequence for specifying color codes

`-e` is used with `echo` as we have special characters/interpretation in the string

In the above example, there are two parts

1. `\e[32mRed`
2. `\e[0m`

Once you issue a COLOR, all the subsequent output on CLI will follow the same color.

So, we start with `Red` and then reset to `Black`

```bash
RED="\e[31m"
ENDCOLOR="\e[0m"
echo -e "${RED}Red Text${ENDCOLOR}"
```

##### Foreground vs Background

Based on the number we use in the special code, the color can be applied to the text (foreground) or the background

_For example_

`\e[31m` is **RED** foreground

`\e[41m` is **RED** background

https://dev.to/ifenna__/adding-colors-to-bash-scripts-48g4