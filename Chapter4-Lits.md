## 4 Lists

### List data type

List value that contains multiple values  
The values is also called items  
Comma-delimited  
You can access items in a list with it's integer index  
The index start from 0  
You can use negative indexes, -1: the last  
You can get multiple items using slices  
The slice has 2 indexes, start from the first index, but not include the last  
len() function, concatenation and replication  
You can convert a value into a list   

```python
>>> lili = ['cat', 'dog', 'mouse']
>>> lili
['cat', 'dog', 'mouse']
>>> lili[0]
'cat'
>>> 
```


List can contain lists:
```python
>>> lolo = [['carrot', 'spinach'],[1,2,3]]
>>> lolo [0]
['carrot', 'spinach']
>>> lolo[1][1]
2
```

Negative indexes:
```python
>>> lili = ['cat', 'dog', 'snake', 'bird', 'mouse']
>>> lili[-1]
'mouse'
```

slice  (from x to y , but not include y)
```python
>>> lili = ['cat', 'dog', 'snake', 'bird', 'mouse']
>>> lili[1:3]
['dog', 'snake']
```

index: single item
slice: list of values


Changing value:
```python
>>> lili = ['cat', 'dog', 'snake', 'bird', 'mouse']
>>> lili[2:4] = ['TIGER', 'ELEPHANT', 'RHINO']
>>> lili
['cat', 'dog', 'TIGER', 'ELEPHANT', 'RHINO', 'mouse']
```

Slice shortcut
```python
>>> lili = ['cat', 'dog', 'snake', 'bird', 'mouse']
>>> lili[:2]
['cat', 'dog']
>>> lili[2:]
['snake', 'bird', 'mouse']
```

Delete from the list:
```python
>>> lili = ['cat', 'dog', 'snake', 'bird', 'mouse']
>>> del lili[2]
>>> lili
['cat', 'dog', 'bird', 'mouse']
```

del = unassignment statement


You can mix:
```python
>>> cooco = ['lala', 1, 3, 'oops']
>>> cooco
['lala', 1, 3, 'oops']
```

List length:
```python
>>> len('hello')
5
>>> len([1,2,3])
3
```

Concatenation
```python
>>> 'hello ' + 'word'
'hello word'
>>> [1,2,3] + [4,5,6]
[1, 2, 3, 4, 5, 6]

>>> 'hello'*3
'hellohellohello'
>>> [1,2,3]*3
[1, 2, 3, 1, 2, 3, 1, 2, 3]
```

tl;dr: string = list of single characters values

### ```list()``` function
```python
>>> int('33')
33
>>> str(33)
'33'
>>> list('hello')
['h', 'e', 'l', 'l', 'o']
```

### ```in``` and ```not``` operators
to check if the value is in or not in the list

```python
>>> 'heiya' in ['hello', 'hij', 'chao', 'heiya']
True

>>> 'hoy' in ['hello', 'hij', 'chao', 'heiya']
False

>>> 'heiya' not in ['hello', 'hij', 'chao', 'heiya']
False
```python

For Loops with List

for loops technically iterates over the values in a list
```python
>>> for i in range(4):
	print(i)
0
1
2
3
```

this is similar to 
```python
>>> range(4)
range(0, 4)
>>> [0,1,2,3]
[0, 1, 2, 3]
```

range() function returns a list-like value, which can be passed to the list() function if you need an actual list value
```python
>>> for i in [0, 1, 2, 3]:
	print(i)
0
1
2
3
```

list like ~ sequence
```python
>>> list(range(4))
[0, 1, 2, 3]

>>> list(range(0, 100, 2))
[0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42, 44, 46, 48, 50, 52, 54, 56, 58, 60, 62, 64, 66, 68, 70, 72, 74, 76, 78, 80, 82, 84, 86, 88, 90, 92, 94, 96, 98]

>>> lolo  =  list(range(0, 100, 2))
>>> lolo
[0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42, 44, 46, 48, 50, 52, 54, 56, 58, 60, 62, 64, 66, 68, 70, 72, 74, 76, 78, 80, 82, 84, 86, 88, 90, 92, 94, 96, 98]
```

### for i in range(len(someList)):

```python
>>> for i in range(len(supplies)):
	print('Index '  + str(i) + ' in supplies is: ' + supplies[i])
Index 0 in supplies is: pens
Index 1 in supplies is: staples
Index 2 in supplies is: paper
Index 3 in supplies is: bin
```

Multiple Assignment:
```python
>>> cat = ['fat', 'orange', 'loud']
>>> size = cat[0]
>>> color = cat[1]
>>> disposition = cat[2]
>>> 
>>> # the same as
>>> size, color, disposition = cat
>>> size
'fat'
>>> color
'orange'
>>> 
>>> size, color, disposition = 'skinny', 'black' , 'quiet'
>>> color
'black'
```

### Swapping Variables

Variables can swap their values using multiple assignment

```python
>>> a = 'AAA'
>>> b = 'BBB'
>>> a,b = b,a
>>> a
'BBB'
>>> b
'AAA'
```

### Augmented Assignment Operators (shortcuts)

```python
>>> lolo = 33
>>> lolo = lolo + 1
>>> lolo
34
>>> ## same as
>>> lolo = 33
>>> lolo += 1
>>> lolo
34

lolo += 1  | lolo = lolo + 1
lolo -= 1   | lolo = lolo - 1
lolo /= 1   | lolo = lolo / 1
lolo %= 1    | lolo = lolo % 1
```


### List Methods

Methods are function that are "called on" values

### ```index()``` : returns the index of an item in the list

```python
>>> lolo = ['hi', 'hello', 'heiya']
>>> lolo.index('hello')
1
```

If there is a duplicate only shows the first match:
```python
>>> lolo = ['hi', 'hello', 'heiya', 'heiya']
>>> lolo.index('heiya')
2
```

### ```append()``` : adds a value anywhere inside the list

```python
>>> animal = ['cat', 'dog', 'mouse']
>>> animal.append('snake')
>>> animal
['cat', 'dog', 'mouse', 'snake']
```

### ```insert()```

```python
>>> animal = ['cat', 'dog', 'mouse']
>>> animal.insert(1, 'snake')
>>> animal
['cat', 'snake', 'dog', 'mouse']
```

### ```remove()```

```python
>>> animal = ['cat', 'dog', 'mouse']
>>> animal.remove('dog')
>>> animal
['cat', 'mouse']
```

```removed()``` only remove the first found element:
```python
animal = ['cat', 'dog', 'mouse', 'cat', 'cat', 'cat']
>>> animal = ['cat', 'dog', 'mouse', 'cat', 'cat', 'cat']
>>> animal.remove('cat')
>>> animal
['dog', 'mouse', 'cat', 'cat', 'cat']
```

### ```del```  (similar to ```remove()```)
```python
>>> animal = ['cat', 'dog', 'mouse']
>>> del animal[0]
>>> animal
['dog', 'mouse']
```

### ```sort()```
```python
>>> lolo = [ 1, 5, 22, 88, -34]
>>> lolo.sort()
>>> lolo
[-34, 1, 5, 22, 88]

>>> animal = ['cat', 'dog', 'mouse', 'cat', 'cat', 'cat']
>>> animal.sort()
>>> animal
['cat', 'cat', 'cat', 'cat', 'dog', 'mouse']
>>> animal.sort(reverse=True)
>>> animal
['mouse', 'dog', 'cat', 'cat', 'cat', 'cat']
```

It's ASCII-betical
```python
>>> animal = ['Cat', 'Dog', 'mouse', 'ant', 'bird']
>>> animal.sort()
>>> animal
['Cat', 'Dog', 'ant', 'bird', 'mouse']
>>> animal.sort(key=str.lower)
>>> animal
['ant', 'bird', 'Cat', 'Dog', 'mouse']
```

### mutable VS immutable data type

String and list are similar, but strings are immutable.

Many things that we can do with list can be done with string
```python
>>> list('hello')
['h', 'e', 'l', 'l', 'o']
>>> name = 'Macarana'
>>> name[0]
'M'
>>> name[-2]
'n'
>>> 'ca' in name
True
>>> 'co' in name
False
>>> for letter in name:
	print(letter)
M
a
c
a
r
a
n
a
```

BUT
list is mutable data type   
string is immutable data type  
tuple is also immutable  

Mutable values like lists can be modified in place.

Immutable values like strings and tuples cannot be modified "in place", hence it does not use reference.

To edit the string:
```python
>>> title = 'Pussy a cat'
>>> newTitle = title[0:6] + 'the ' + title[8:12]
>>> newTitle
'Pussy  the cat'
```

The difference between immutable and mutable comes up with "references" 

mutable: uses reference (ex: list)  
immutable: does not user reference (ex: string)

variable store value like below, copy whatever value from one variable to another:
```python
>>> lolo = 33
>>> lili = lolo
>>> lili = 22
>>> lili
22
>>> lolo
33
```

But list don’t work quite the same, when we assign a list, we assign a list variable:
```python
>>> roro = [0,1,2,3]
>>> riri = roro
>>> riri[1] = 'hello'
>>> riri
[0, 'hello', 2, 3]
>>> roro
[0, 'hello', 2, 3]
```

We're assigning a reference to riri

Variables don't contain lists, they contain references to lists.

When passing a list argument to a function, you are actually passing a list reference.

```python
def eggs(someParameter):
    someParameter.append('hello')
spam = [1, 2, 3]
eggs(spam)
print(spam)

# OUTPUT:
[1, 2, 3, 'hello']
```

Note: the added value should have been local variable, but not for the case of reference

Changes made to a list in a function will affect the list outside the function.

### ```copy()```
```python
>>> import copy
>>> animal = ['cat', 'dog', 'mouse']
>>> living = copy.deepcopy(animal)
>>> living[1] = 'croc'
>>> animal
['cat', 'dog', 'mouse']
>>> living
['cat', 'croc', 'mouse']

Multiple lines:

>>> animal= [ 'cat',
	      'dog',
	      'bird']
>>> animal
['cat', 'dog', 'bird']
```

or use \ line continuation character  to stretch Python instruction across multiple lines.

````
>>> print ('at this moment ' + \
       'you should be...')
at this moment you should be...
