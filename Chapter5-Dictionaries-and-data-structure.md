# 5 Dictionaries

Dictionary, like a List is a collection of many values
Unlike List indexes, Dictionary can use many data types, not just integers

Dictionaries contain key:value pairs. Keys are like a list's indexes.

Dictionaries are mutable. Variables hold references to dictionary values, not the dictionary value itself.

{key: value}


```python
>>> myCat = { 'size': 'fat', 'color': 'gray', 'disposition': 'loud'}
>>> myCat['size']
'fat'
>>> 'My cat has ' + myCat['color'] + ' fur.'
'My cat has gray fur.'
```

## Dictionaries vs List

Unlike List, the items in Dictionary are unordered.

```python
>>> [1, 2, 3] == [3, 2, 1]
False
```

```python
>>> eggs = {'name': 'Zophie', 'species': 'cat', 'age': '8'}
>>> ham = {'species': 'cat', 'age': '8', 'name': 'Zophie'}
>>> eggs == ham
True
```

### ```in``` & ```not``` in
```python
>>> eggs = {'name': 'Zophie', 'species': 'cat', 'age': '8'}
>>> 'name' in eggs
True
>>> 'name' not in eggs
False
>>> 'Zophie' in eggs
False
```


### ```keys()```, ```values()```, and ```items()```

The ```keys()```, ```values()```, and ```items()``` methods will return list-like values of a dictionary's keys, values, and both keys and values, respectively.

```python
>>> eggs = {'name': 'Zophie', 'species': 'cat', 'age': '8'}
>>> list(eggs.keys())
['name', 'species', 'age']
>>> list(eggs.values())
['Zophie', 'cat', '8']
>>> list(eggs.items())
[('name', 'Zophie'), ('species', 'cat'), ('age', '8')]

>>> eggs = {'name': 'Zophie', 'species': 'cat', 'age': '8'}
>>> eggs.keys()
dict_keys(['name', 'species', 'age'])
>>> for k in eggs.keys():
	print(k)
name
species
age

>>> for v in eggs.values():
	print(v)
Zophie
cat
8

>>> for k,v in eggs.items():
	print (k, v)
name Zophie
species cat
age 8

>>> for i in eggs.items():
	print(i)
('name', 'Zophie')
('species', 'cat')
('age', '8')
>>> 

>>> eggs = {'name': 'Zophie', 'species': 'cat', 'age': '8'}
>>> 'cat' in eggs.values()
True
```

### ```get()``` Method

The ```get()``` method can return a default value if a key doesn't exist.

```python
>>> eggs = {'name': 'Zophie', 'species': 'cat', 'age': '8'}
>>> eggs.get('age', 0)
'8'
>>> eggs.get('color', '')
''

>>> picnicItems = {'apples': 5, 'cups': 2}
>>> 'I am bringing ' + str(picnicItems.get('cups', 0)) + ' cups.'
'I am bringing 2 cups.'
>>> 'I am bringing ' + str(picnicItems.get('eggs', 0)) + ' eggs.'
'I am bringing 0 eggs.'
```

### ```setdefault()``` Method


The ```setdefault()``` method can set a value if a key doesn't exist.

```python
>>> eggs = {'name': 'Zophie', 'species': 'cat', 'age': '8'}
>>> if 'color' not in eggs:
	eggs['color'] = 'black'
>>> eggs
{'name': 'Zophie', 'species': 'cat', 'age': '8', 'color': 'black'}

>>> eggs = {'name': 'Zophie', 'species': 'cat', 'age': '8'}
>>> if 'color' not in eggs:
	eggs['color'] = 'black'
```

same as: 
```python
>>> eggs = {'name': 'Zophie', 'species': 'cat', 'age': '8'}
>>> eggs.setdefault('color', 'black')
'black'
>>> eggs
{'name': 'Zophie', 'species': 'cat', 'age': '8', 'color': 'black'}
>>> # BUT
eggs.setdefault('color', 'orange')  # this does not change anything as there is already
'black'
>>> eggs
{'name': 'Zophie', 'species': 'cat', 'age': '8', 'color': 'black'}
```

Set default does not change anything if the value already exists


```python
message = 'A practical programming course for office workers, academics, and administrators who want to improve their productivity.'
count = {}  # key value pairs, key:character, value: how many times it appear in the message, ex: 'r' : 12
for character in message:
    count.setdefault(character, 0)
    count[character] = count[character] + 1
print(count)

# OUTPUT:
{'A': 1, ' ': 15, 'p': 4, 'r': 12, 'a': 9, 'c': 7, 't': 8, 'i': 10, 'l': 1, 'o': 10, 'g': 2, 'm': 5, 'n': 4, 'u': 2, 's': 5, 'e': 6, 'f': 3, 'w': 3, 'k': 1, ',': 2, 'd': 4, 'h': 2, 'v': 2, 'y': 1, '.': 1}
```

The above program is not optimum because it distinguishes between upper & lower cases.

```python
message = 'A practical programming course for office workers, academics, and administrators who want to improve their productivity.'
count = {}  # key value pairs, key:character, value: how many times it appear in the message, ex: 'r' : 12
for character in message.upper():
    count.setdefault(character, 0)
    count[character] = count[character] + 1
print(count)

# OUTPUT:
{'A': 10, ' ': 15, 'P': 4, 'R': 12, 'C': 7, 'T': 8, 'I': 10, 'L': 1, 'O': 10, 'G': 2, 'M': 5, 'N': 4, 'U': 2, 'S': 5, 'E': 6, 'F': 3, 'W': 3, 'K': 1, ',': 2, 'D': 4, 'H': 2, 'V': 2, 'Y': 1, '.': 1
```

### ```pprint()``` Pretty Print
The pprint module's ```pprint()``` "pretty print" function can display a dictionary value cleanly. The pformat() function returns a string value of this output.

```python
import pprint
message = 'A practical programming course for office workers, academics, and administrators who want to improve their productivity.'
count = {}  # key value pairs, key:character, value: how many times it appear in the message, ex: 'r' : 12
for character in message.upper():
    count.setdefault(character, 0)
    count[character] = count[character] + 1
pprint.pprint(count)

# OUTPUT:
{' ': 15,
 ',': 2, 
 '.': 1, 
 'A': 10,
 'C': 7,
 'D': 4,
 'E': 6,
 'F': 3,
 'G': 2,
 'H': 2,
 'K': 1,
 'L': 1,
 'M': 5,
 'N': 4,
 'O': 10,
 'P': 4,
 'R': 12,
 'S': 5,
 'T': 8,
 'U': 2,
 'V': 2,
 'W': 3,
 'Y': 1}
 ```


if we want it the output as a string: 
```python
rjtext = pprint.pformat(count)
print(rjtext)
```

## Data structure

we can have a list of dictionaries

```python
>>> cat = {'name': 'pussy', 'age' : 8, 'color' : 'black'}
>>> allCats = []
>>> allCats.append({'name': 'pussy', 'age' : 8, 'color' : 'black'})
>>> allCats.append({'name': 'romeo', 'age' : 4, 'color' : 'gray'})
>>> allCats.append({'name': 'isid', 'age' : 2, 'color' : 'white'})
>>> allCats.append({'name': '???', 'age' : -1, 'color' : 'orange'})
>>> allCats
[{'name': 'pussy', 'age': 8, 'color': 'black'}, {'name': 'romeo', 'age': 4, 'color': 'gray'}, {'name': 'isid', 'age': 2, 'color': 'white'}, {'name': '???', 'age': -1, 'color': 'orange'}]
>>> 
```

### TicTacToe

```python
>>> theBoard = {'top-L': ' ', 'top-M': ' ', 'top-R': ' ',
            'mid-L': ' ', 'mid-M': ' ', 'mid-R': ' ',
            'low-L': ' ', 'low-M': ' ', 'low-R': ' '}
>>> import pprint
>>> pprint.pprint(theBoard)
{'low-L': ' ',
 'low-M': ' ',
 'low-R': ' ',
 'mid-L': ' ',
 'mid-M': ' ',
 'mid-R': ' ',
 'top-L': ' ',
 'top-M': ' ',
 'top-R': ' '}

>>> theBoard['mid-M'] = 'X'
>>> pprint.pprint(theBoard)
{'low-L': ' ',
 'low-M': ' ',
 'low-R': ' ',
 'mid-L': ' ',
 'mid-M': 'X',
 'mid-R': ' ',
 'top-L': ' ',
 'top-M': ' ',
 'top-R': ' '}

>>> def printBoard(board):
    print(board['top-L'] + '|' + board['top-M'] + '|' + board['top-R'])
    print('-+-+-')
    print(board['mid-L'] + '|' + board['mid-M'] + '|' + board['mid-R'])
    print('-+-+-')
    print(board['low-L'] + '|' + board['low-M'] + '|' + board['low-R'])
>>> printBoard(theBoard)
 | | 
-+-+-
 |X| 
-+-+-
 | | 
 ```


list & dictionary can be combined to represent a real life objects

```python
type()
>>> type(33)
<class 'int'>
>>> type('hello')
<class 'str'>
>>> type(3.14)
<class 'float'>
>>> type(theBoard)
<class 'dict'>
>>> type(theBoard['top-R'])
<class 'str'>
```
