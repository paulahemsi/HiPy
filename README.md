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

## List

Lists are one of the most powerful data types in Python. They’re used to store related items together.

[List cheat sheet](https://practical.learnpython.dev/02_data_types/30_lists/) from Nina Zakharenko

| type | list |
| ---- | ---- |
| use | Used for storing similar items, and in cases where items need to be added or removed |
| creation | `[]` or `list()` for empty list, or `[1, 2, 3]` for a list with items |
| search methods | `my_list.index(item)` or `item in my_list` |
| search speed | Searching for an item in a large list is slow brcause each item must be checked |
| common methods | `len(my_list)`, `append(item)` to add, `insert(index, item)` to insert at index, `pop()` to remove |
| order preserved? | Yes. Items can be accessed by index. |
| mutable? | yes |
| in-place sortable?| Yes. `my_list.sort()` will sort the list in-place. `my_list.sort(reverse=True)` will sort the list in-place in descending order. `my_list.reverse()` will reverse the items in *my_list* in-place. |

| action | method | returns | possible errors |
| ------ | ------ | ------- | --------------- |
| check length | `len(my_list)` | int |  |
| **add** to the end | `my_list.append(item)` | - |  |
| **insert** at position | `my_list.insert(pos, item)` | - |  |
| **update** at position | `my_list[pos] = item` | - |  |
| **extend**: add items from another list | `my_list.extend(other_list) | - | |
| is item in list? | `item in my_list` | `true` or `false` | |
| **index** of item | `my_list.index(item)` | int | `ValueError` if `item` is not in `my_list` |
| **count** of item | `my_list.count(item)` | int | |
| **remove** an item | `my_list.remove(item)` | - | `ValueError` if `item` is not in `my_list` |
| **remove** the last item, or an item at an index| `my_list.pop()` or `my_list.pop(pos)`| `item` | `IndexError` if `pos` >= `len(my_list)` |

### List x Array

Font: [this article](https://learnpython.com/blog/python-array-vs-list/) from Kateryna Koidan

| List | Array |
| ---- | ----- |
| built-in| import from *NumPy* package or *array* module |
| ordered | ordered |
| mutable | mutable |
| able to store non-unique| able to store non-unique items |
| elements can be of different data types | imported from *array module* elements must be of the same type|
| elements can be of different data types | *NumPy* arrays support different data types|
| don't need to be declared | need to be declared *array.array()* *numpy.array()*|
| cannot directly handle math operations | are great for numerical operations |
| less efficient for storing large amounts of data | can store data very compactly, more efficient |


## Helpufull REPL methods

typeof() is `type()`

`dir()` shows all the methods available for the given parameter (str, int, variables names, etc)

`help()` pass a class as parameter or a method (str.replace)
