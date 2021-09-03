# HiPy
Python studies

## Setup

`python3 -m venv env`

`-m` run command as a module

`venv` create a virtual environment

`env` standart name for directory, already in gitignore

`source env/bin/activate` activate virtual environment

### usefull vscode shortcuts

`ctrl + p` quick open
`ctrl + shift + p` show command Palette

## Why Python

quick, open source, active community, rich standard library

## Variables 

should be named in lowercase and start with a letter or an underscore

be as descriptive as possible cause python is a dynamic language

snake case `my_variable_name`

Null in python is `None`

## Numbers

points make numbers floats `3.0` `0.` `-19.7`

float(5) converts int 5 to float, all types are methods under the hood

two integers division will result in a float, to force the result to be integer, we can use two slashes

```
> > > 25 / 5
5.0
> > > 25 // 5
5
> > > 25 / 6
4.16666666
> > > 25 // 6
4
```

`**` power of
```
> > > 4 ** 3
64
```

`min()` pick the smallest number passed as parameter
`max()` pick the higher number passed as parameter
`round()` round number passed as parameter

## Strings

`'` and `"` are acepted but `"` are better to nested `'` inside

`\n` `\t` works like in C

`print()` prints the given(s) parameter(s) (if separated by `,`, prints puts the space for us)

```
> > > print("hi", "you")
hi you
```
`f` concatenates the string with variables between `{}`

```
> > > print(f"hi {number_variable}")
hi 13
```

`+` concatenates strings

string method `.replace` replace the char(s) passed as first parameter for the char(s) passed as second parameter

`strip()` returns a new string after removing any leading and trailing whitespace

`rstrip()` does the same but only removes trailing whitespace

`lstrip()` only trims leading whitespace

## Helpufull REPL methods

typeof() is `type()`

`dir()` shows all the methods available for the given parameter (str, int, variables names, etc)

`help()` pass a class as parameter or a method (str.replace)
