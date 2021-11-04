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

strings are immutable

`'` and `"` are acepted but `"` are better to nested `'` inside

`\n` `\t` works like in C

`print()` prints the given(s) parameter(s) (if separated by `,`, prints puts the space for us)

`from pprint import pprint` `pprint()` pretty print

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
Lists are **mutable**

[List cheat sheet](https://practical.learnpython.dev/02_data_types/30_lists/) by Nina Zakharenko

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

to sort without change the original list, we can use `sorted(my_list)` or `sorted(my_list, reverse=True)` for reverse sorting

`+` concatenates lists

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
| **remove** the last item, or an item at an index| `my_list.pop()` or `my_list.pop(pos)`| `item` removed | `IndexError` if `pos` >= `len(my_list)` |

### List x Array

Font: [this article](https://learnpython.com/blog/python-array-vs-list/) by Kateryna Koidan

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

## Tuple

tuples are **immutable**

[Tuplecheat sheet](https://practical.learnpython.dev/03_sets_tuples_dicts/10_tuples/) by Nina Zakharenko

```
Tuples are light-weight collections used to keep track of related, but different items.
While lists are generally used to store collections of similar items together, tuples, by contrast, can be used to contain a snapshot of data. 
A good use of a tuple might be for storing the information for a row in a spreadsheet. 
We don’t necessarily care about updating or manipulating that data, we just want a read-only snapshot.
```

| type | tuple |
| ---- | ---- |
| use | Used for storing a snapshot of related items when we don’t plan on modifying, adding, or removing data |
| creation | `(,)` or `tuple()` for empty tuple. `(1, )` for one item, or `(1, 2, 3)` for a tuple with several items |
| search methods | `my_tuple.index(item)` or `item in my_tuple` |
| search speed | Searching for an item in a large tuple is slow. Each item must be checked |
| common methods | `Can’t add or remove from tuples |
| order preserved? | Yes. Items can be accessed by index. |
| mutable? | No |
| in-place sortable?| No |

getting multiple itens from the tuple:

```
student = ("Paula", 34, "Philosophers", 100)
name, age, project, grade = student
```

with a placeholder if there'a any value I dont care at the time:

```
student = ("Paula", 34, "Philosophers", 100)
name, age, project, _ = student
```


## Set

mutable datatype to store **immutable** types in an unsorted way

no duplicates allowed

empty set must be created with `set()` cause `{}` will create a dict

[Set cheat sheet](https://practical.learnpython.dev/03_sets_tuples_dicts/20_sets/) by Nina Zakharenko

| type | set |
| ---- | ---- |
| use | Used for storing immutable data types uniquely. Easy to compare the items in sets |
| creation | `set()` for an empty set (`{}` makes an empty `dict`) and `{1, 2, 3}` for a set with items in it|
| search methods | `item in my_set` |
| search speed | Searching for an item in a large set is very fast |
| common methods | `my_set.add(item)`, `my_set.discard(item)` to remove the item if it’s present, `my_set.update(other_set)` |
| order preserved? | **No.** Items can’t be accessed by index. |
| mutable? | **Yes.** Can add to or remove from sets. |
| in-place sortable?| **No**, because items aren’t ordered. |


## Dictionaries

[Dictionaries cheat sheet](https://practical.learnpython.dev/03_sets_tuples_dicts/30_dictionaries/) by Nina Zakharenko

dict are **mutable** keys can only be immutable types.

| type | dict |
| ---- | ---- |
| use | Use for storing data in key, value pairs. Keys used must be **immutable** data types. |
| creation | `{}` or `dict()` for an empty dict. `{1: "one", 2: "two"}` for a dict with items.|
| search methods | `key in my_dict` |
| search speed | Searching for a key in a large dictionary is fast |
| common methods | `my_dict[key]` to get the value by *key*, and throw a *KeyError* if *key* is not in the dictionary. Use `my_dict.get(key)` to fail silently if *key* is not in *my_dict*. `my_dict.items()` for all key, value pairs, `my_dict.keys()` for all keys, and `my_dict.values()` for all values. |
| order preserved? | **Sort of**. As of Python 3.6 a dict is sorted by insertion order. Items can’t be accessed by index, only by key. |
| mutable? | **Yes**. Can add to or remove from `dicts`. |
| in-place sortable?| **No**. `dicts` don’t have an index, only keys. |

`{ key : value }`

`my_dict.get(key, <optional exeption>)` if the key doesn't exist, it will return the given exeption

`my_dict[key] = value` to replace or insert new values

`my_dict.update(my_other_dict)` like in sets

if the value is, for eg, a list, we can do all the lists operations with it, as we know that py_dict[key]
will return a list (same with objects, etc)

```
To avoid subtle bugs, we can check if a particular key is in a dictionary with the `in` keyword
```

`del my_dict["element"]` deletes the element, but is preferred to use `pop` instead, since it returns the deleted value and deal better with possible errors:

```
pop(...)
    D.pop(k[,d]) -> v, remove specified key and return the corresponding value.
    
    If key is not found, default is returned if given, otherwise KeyError is raised
```

## Helpufull REPL methods

typeof() is `type()`

`dir()` shows all the methods available for the given parameter (str, int, variables names, etc)

`help()` pass a class as parameter or a method (str.replace)

`hash(var)` is a shortcut to check for mutability, hash with mutable types will raise an error

## Function

`def` + `function_name` + `(<optional argument> , <optional arguments> , <etc>)` + `:`
`tab`

```py

def my_function():
	print("hi")

```

Functions can accept arguments with or without default values.
All of the required arguments go first. They are then followed by the optional keyword arguments (those with default values).

```py

def my_function(word):
	print(word)

my_function("hi")
>>>'Hi'
```

```py

def my_function(word, end="bye"):
	print(word, end)

my_function("hi,")
>>>'Hi, bye'

my_function("hi,", "tchau")
>>>'Hi, tchau'
```

It's possible to pass arguments by name, in this case in any order cause they're labeled

```py
my_function(end="adios", word="Hola,")
>>>'Hola, adios'
```

```
Never use mutable types, like lists as a default argument.
```

[The Naming of Ducks: Where Dynamic Types Meet Smart Conventions Video](https://www.youtube.com/watch?v=YklKUuDpX5c)


## Truthiness

**ints** work like in C, **0** is `False`, all others are `True`

empty **strings**, **lists**, **tuples**, **sets** or **dicts** are `False`

**strings**, **lists**, **tuples**, **sets** or **dicts** with at least one value are `True`

`==` and `!=` check for **equality** of the contents

`is` and `is not` check for **identity**, if is pointing to the same place in memory


use `is` to check for **None** ou **True** \ **False**


`bool(3 < 5)` answers true or false

## Boolean Operators

`or` == `||`
`and` == `&&`
`not` == `!`

## Control Statements

`if` `elif` `else`

## Loops

for loop:

`for single_item in items` 

`single_item` temporary loop variable, but still acessible outside the loop scope (with the last value from the iteration)
`items` sequece of items

```py
>>> animals = ["owl", "cat", "dog", "bird"]
>>> for animal in animals:
	print(f"Animal: {animal}")
	
Animal: owl
Animal: cat
Animal: dog
Animal: bird
```

`range()` produces a sequence of integers (optional -default 0- and *inclusive* start to defined *exclusive* finish)


```py
>>> for number in range(7, 13):
		printf(number)
		
7
8
9
10
11
12
```

In python we don't need to have an index variable to increment, enumerate function handles that, returning a list of tuples (containing the index and the item) from a sequence

```bash
class enumerate(object)
 |  enumerate(iterable, start=0)
 |  
 |  Return an enumerate object.
 |  
 |    iterable
 |      an object supporting iteration
 |  
 |  The enumerate object yields pairs containing a count (from start, which
 |  defaults to zero) and a value yielded by the iterable argument.
 |  
 |  enumerate is useful for obtaining an indexed list:
 |      (0, seq[0]), (1, seq[1]), (2, seq[2]), ...
```
more info and methods in `help(enumerate)`

```py
>>> animals = ["owl", "cat", "dog", "bird"]
>>> for index, animal in enumerate(animals):
	print(f"Animal: {animal}, index: {index}")
	
Animal: owl, index: 0
Animal: cat, index: 1
Animal: dog, index: 2
Animal: bird, index: 3
```

Looping over a dictionary with `for item in my_dict`, will loop just over the keys, but with the method `.items()` that unpacks the dictionary into a tuple, we are able to loop over keys and values

```py
>>> hex_colors = {
		"Red": "#FF0000",
		"Green": "#008000",
		"Blue": "#0000FF",
	}
>>> for color, hex_value in hex_colors.items():
	     print(f"For color {color}, the hex value is: {hex_value}")
	
For color Red, the hex value is: #FF0000
For color Green, the hex value is: #008000
For color Blue, the hex value is: #0000FF
```

> There's no ++ in python

**True** **False** Python vs C **true** **false**

```py
for i in [0, 1, 2]:
	print("for loop")
```

is the same of

```py
for i in range(3):
	print("for loop")
```

cause `range` generates a list of 3 (or the number passed as parameter)

range(0, 101, 2) will go from 0 to 100 all 2 stepts at a time

`range(stop)`
`range(start, stop[, step])`

List is very similar to an Array

`rstrip()` function cut the withespaces from a string

```py
words = set()

def load(dictionary):
	file = open(dictionary, "r")
	for line in file:
		words.add(line.rstrip())
```

`in`

```py
from CS50 import get_string

s = get_string("Do you agree? ")

if s.lower() in ["y", "yes"]:
	print("Agreed. ")
elif s.lower() in ["n", "no"]:
	print("Not Agreed.")
```

variables created inside a function have the whole function scope, even if they were created inside a loop

```py
from CS50 import get_int

def get_positive_int():
	while True:
		n = get_int("Positive Integer: ")
		if n > 0:
			break
	return n
```

`print` has a lot of optional arguments, like `end` to set another end character (or string) then `\n`
or the hability of make matematical operations

```py
for i in range(4):
	print("?". end="")

>> ????


print("?" * 4)

>> ????
```




```py

scores = [72, 73, 33]

print("Average: " + str(sum(scores) / len(scores)))

# same of:

print(f"Average: {sum(scores) / len(scores)}") #here the str() isn't necessary cause is inside a formated string and python do the conversion to us


```


**Argv in python**

there's no argc C, but argv is a list so we can access the len with len(argv) or iterate over all the args with `in` 

```py
from sys import argv

for arg in argv:
    print(arg)

```

sys package also includes the `exit` function, that works like in C

Pointers are not accesible anymore, but they still exist underneath the hood

```py
x = 1
y = 2

print(f"x is {x}, y is {y}")

x, y = y, x

print(f"x is {x}, y is {y}")

>> x is 1, y is 2
>> x is 2, y is 1

```

## List Comprehensions

short sintaxe for create lists looping over a list in python

`[<value> for <vars> in <iter>]`

```py
pets = ["dog", "cat", "parrot", "turtle"]
my_list = []
for pet in pets:
	my_list.append(len(pet))
```

is the same of:

```py
my_list = [len(pet) for pet in pets]

```

and with condicional:

```py
my_list = [pet for pet in pets if len(pet) % 2 == 0]

```

composed, generating a list of tuples:

```py
my_list = [(pet, len(pet)) for pet in pets]
```

strings operations:

```py
my_pets = ", ".join([pet for pet in pets])

```
number operations:

```py
my_sum = sum([num for num in range(0, 100) if num % 3 == 0])
```
