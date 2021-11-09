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

`f` concatenates the string with variables between `{}` and can be used in any function that receives a string as argument

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

## Files

`r` reading (default)
`w` writing (truncating)
`x` exclusive creation (fails if the file already exists)
`a` writing (appending)
`b` binary
`t` text (default)
`+` open a disk file for updating

```py
import csv

file = open("phonebook.csv", "a") #a append

name = get_string("Name: ") #cs50 lib
number = get_string("Number: ") #cs50 lib

writer = csv.writer(file)

wirter.writerow([name, number])

file.close()
```

is the same of:

```py
import csv

with open("phonebook.csv", "a") as file:
	name = get_string("Name: ") #cs50 lib
	number = get_string("Number: ") #cs50 lib

	writer = csv.writer(file)

	wirter.writerow([name, number]
# this with keyword closes the file for us
```

`with` is a context manager, wrapping the block of code that depends on some resource and cleanning up at the end, even in the case the code inside receives an exception

google form with Harry Potter houses preferences

```py
import csv

houses = {
	"Gryffindor": 0,
	"Hefflepuff": 0,
	"Ravenclaw": 0,
	"Slytherin": 0
}

with open("form.csv". "r") as file
	reader = csv.reader(file)
	next(reader) # to skip the first row (header)
	for row in reader:
		house = row[1] #first row field was timestamp
		houses[house] += 1

for house in houses:
	print(f"{house}: {houses[house]}")
```

## in keyword

```py
words = input("Saying something: ").lower()

if "hello" in words:
	print("Hello to you too!")
elif "how are you" in words:
	print("I am well, thanks")
elif "goodbye" in words:
	print("Goodbye to you too!")
else:
	print("huh?")
	
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

there's also **Dictionary Comprehensions**, **Set Comprehensions** and **Generator Expressions**

>Generator expressions are a more advanced concept. A generator is a type of iterable object - like a list, you can iterate through each element - however, unlike a list, generators evaluate elements on demand, instead of assembling them all at once.

more informations about them in [this amazing guide](https://practical.learnpython.dev/05_practical_applications/10_other_comprehensions/) by Nina Zakharenko

## Slicing 

easy way to create sub-lists from larger lists

```py
>>> my_string = "Hello, world!"
>>> my_string[7:12] # from 7 to 12
'world'
>>> my_string[:5] # from zero to 5
'Hello'
>>> my_string[7:] # from 7 to the end
'world!'
```

`my_list[:]` shortcut to make a copy, from beggining to end

## Zip

The zip function takes any number of iterable arguments and steps through all of them at the same time until the **end of the shortest iterable** has been reached

```py
>>> names = ["Ann", "Leah", "Martha", "Ruth"]
>>> grades = [95, 70, 89]
>>> for name, grade in zip(names, grades):
>>>     print(f"{name} had a grade of {grade}")

Ann had a grade of 95
Leah had a grade of 70
Martha had a grade of 89
```
zip() is very usefull to create dictionaries from two lists:

```py
>>> names = ["Ann", "Leah", "Martha"]
>>> grades = [95, 70, 89]
>>> student_dict: dict(zip(names, grades))
>>> print(student_dict)
{'Ann': 95, 'Leah': 70, 'Martha': 89}
```
>the result of calling the zip function is actually a generator under the hood. You can only loop over the result of zipping once. If you try to loop over it again, the result will be empty.

## OOP in Python

Languages that adopt an Object-oriented style organize things into objects, and provide methods for objects to communicate with one another.

everything in python is an object and almost everything has attributes and methods

Objects are center-stage in Python, representing not only the data, but the overall structure of the programs as well

## self

`self` refers to an instance inside her class (like `this` in c++)

```py
class Car:
	runs = True

	def start(self): #method that requires an instance
		if self.runs:
			print("Car is started. Vroom vroom!")
		else:
			print("Car is bronken :(")
```

In C++ the instance `this` is passed as argument to all class method, but in python we need to specify if we want this behaviour or not with the keyword `self` as a parameter

`TypeError: my_method() takes 0 positional arguments but 1 is given`: when we call a method in an instance without specifiyng in the method that it need to recieve `self` as parameter.

## Methods

`@classmethod` above a method definition defines that method as a class method, 
and receive the class as parameter

```py
class Car:
    runs = True
    number_of_wheels = 4

    @classmethod
    def get_number_of_wheels(cls):
        return cls.number_of_wheels

    def start(self):
        if self.runs:
            print("Car is started. Vroom vroom!")
        else:
            print("Car is broken :(")

my_car = Car()
print(f"Cars have {Car.get_number_of_wheels()} wheels.")

# Of course, we can override this in our instance:
my_car.number_of_wheels = 6

# And when we access our new instance variable:
print(f"My car has {my_car.number_of_wheels} wheels.")

# But, when we call our class method on our instance:
print(f"My car has {my_car.get_number_of_wheels()} wheels.")
```
```
output
Cars have 4 wheels.
My car has 6 wheels.
My car has 4 wheels.
```

## instance

`isinstance(instance, class)` to check if some variable is an instance of some class

```py
>>> isinstance(42, int)
True
>>> isinstance("blah", int)
False
```

`issubclass(class_one, class_two)` to check if a class is a subclass of the other

## Magic methods

`__magic_method__` with two underscores before and after the method name

`dunder` = double underscore

`__init__` inside a class works like a constructor, beeing called when an instance is created

```py
class My_class:

    def __init__(self, name, number):
        self.name = name
        self.number = number
```

`__str__` return a string in a readable way of that object
`__repr__` return a string with the python code necessary to rebuild that object

```py
>>> import datetime
>>> now = datetime.datetime.now()
>>> str(now)
'2019-03-16 21:04:01.396256'
>>> repr(now)
'datetime.datetime(2019, 3, 16, 21, 4, 1, 396256)'
```

Is interesting to also set those methods in our custom classes

## Inheritance

```py

class Baseclass:

	def __init__(self, var1, var2, var3="default")
		self.var1 = var1
		self.var2 = var2
		self.var3 = var3

class Subclass(Baseclass):
	
	def __init__(self, var1, var2, var3="default")
		super().__init__(var1, var2, var3)
```
