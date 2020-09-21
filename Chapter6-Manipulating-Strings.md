# 6 Manipulating Stings

## String Literals

### Double quote

```python
>>> 'that's my cat'
SyntaxError: invalid syntax
>>> "that's my cat"
"that's my cat"
```

### Escape Characters

```python
>>> "that's my cat"
"that's my cat"
```

| Escape Character | Prints as | 
| :----------------|:---------:|
| \' | single quote |
| \" | double quote|
| \t | tab |
| \n | newline (line break) |
| \\\ | backslash |

```python
>>> print("hola \nque tal \nbien")
hola 
que tal 
bien
```

### Raw Stings

*Raw string* completely ingores all escape characters  
Place ```r``` before quote 

```python
>>> print(r"hola \nque tal \nbien")
hola \nque tal \nbien
```
### Multiline Strings with Triple quotes

```python
>>> print(''' Dear alice,
the cat has been arested

sincerely,
Bob''')
 Dear alice,
the cat has been arested

sincerely,
Bob
>>> 
```
If store multiline and display it again we can see the escape character:
```python
>>> lala = ''' Dear alice,
the cat has been arested

sincerely,
Bob'''
>>> lala
' Dear alice,\nthe cat has been arested\n\nsincerely,\nBob'
```
Works with ```'''``` and ```"""```  
Often used for multiline comments

## Indexing and Slicing Strings

You can think ```'hello world``` as list:  
```python
>>> lala = 'hello world'
>>> lala[0]
'h'
>>> lala[3]
'l'
>>> lala[-1]
'!'
>>> lala[0:5]
'hello'
>>> lala[:5]
'hello'
>>> lala [6:]
'world!'
>>> lili = lala[0:5]
>>> lili
'hello'
```

### ```in``` and ```not``` with Strings

```python
>>> lala = 'hello world'
>>> 'hello' in lala
True
>>> 'x' in lala
False
>>> 'cat' not in 'cats and dogs'
False
```


## Useful String Methods: ```upper()```, ```lower()```, ```islower()```

### ```upper()```

```python
>>> lala = 'hello world'
>>> lala = lala.upper()
>>> lala
'HELLO WORLD'
```

Useful to make case-insensitive comparision:  

```python
>>> answer = input()
yes
>>> answer
'yes'
>>> answer = input()
YES
>>> answer
'YES'
>>> 
>>> if answer == 'yes':
	print('playing again')

>>> answer == 'yes'
False
```

 ### ```lower()```
 
 ```python
 print('que tal?')
feeling = input()
if feeling.lower() == 'great':
    print('i feel great too')
else:
    print('i hope it will be great')
 ```
 
### ```islower()``` & '```isupper()```

```python
>>> lala = 'Hello world'
>>> lala.islower()
False
>>> lala.isupper()
False
>>> 'HOLA'.isupper()
True
>>> '1234qwerrt'.islower()
True
>>> 'qwert123'.islower()
True
>>> '12345'.islower()
False
>>> '12345QWERTY'.isupper()
True
>>> '12345'.isupper()
False
```

## The isX String Methods

```isalpha()```   only letters and is not blank  
```isalnum()```  only letters and/or numbers and it is not blank  
```isdecimal()```  numeric chars and not blank  
```isspace()```  spaces, tabs, newlines and not blank  
```istitle()```  worlds begin wiht upper case

```python
>>> 'hello'.isalpha()
True
>>> 'qwerty'.isalpha()
True
>>> 'qwerty123'.isalpha()
False
>>> 'qwerty123'.isalnum()
True
>>> 'qwerty'.isalnum()
True
>>> '123'.isdecimal()
True
>>> '    '.isspace()
True
>>> 'This Is Title'.istitle()
True
>>> 'This Is a Title'.istitle()
False
>>> 'This IS Title'.istitle()
False
```

It's useful when we need to validate user input:
```python
while True:
    print('Enter age:')
    age = input()
    if age.isdecimal():
        break
    print('please enter age in number')
    
while True:
    print('select password, letters and numbers only:')
    password = input()
    if password.isalnum():
        break
    print('password can only have letters and numbers')

### OUTPUT:
Enter age:
qwerty
please enter age in number
Enter age:
34
select password, letters and numbers only:
*
password can only have letters and numbers
select password, letters and numbers only:
122
```


### ```startwith()``` & ```endwith()``` String Method


```python
>>> "Hello world!".startswith('Hello')
True
>>> "Hello world!".endswith('world!')
True
```

### ```join()``` & ```split()``` String Method

```join()``` gets passed a list of strings and returns a string  
```python
>>> ', '.join(['kucing', 'anjing', 'sapi'])
'kucing, anjing, sapi'
>>> 
>>> ' '.join(['my', 'name', 'is', 'Bond'])
'my name is Bond'
```

```split()``` does the opposite  
```python
>>> 'my name is Bond'.split()
['my', 'name', 'is', 'Bond']

>>> 'myABCnameABCisABCBond'.split('ABC')
['my', 'name', 'is', 'Bond']

```

Common useof ```split()``` is to split a multiline string along the newline characters   
```python
>>> lala = '''Hola
It is impossible to know & remember everything about InfoSec.
I have too many notes and cheat sheets scattered in so many places, it’s time to start writing them in one place. 
Some of these notes might not make sense to you, but it makes sense to me.'''
>>> lala.split('\n')
['Hola', 'It is impossible to know & remember everything about InfoSec.', 'I have too many notes and cheat sheets scattered in so many places, it’s time to start writing them in one place. ', 'Some of these notes might not make sense to you, but it makes sense to me.']
```

## Justifying tex with ```rjust()```, ```ljust()```, ```center()```

```python
>>> 'hola'.rjust(10)
'      hola'
>>> 'hola'.ljust(10)
'hola      '
>>> 'hola'.rjust(10, "*")
'******hola'
>>> 'hola'.center(10, "*")
'***hola***'
```

Useful when printing tabular:   
```python
def printPicnic(itemsD, leftW, rightW):
    print('PICNIC ITEMS'.center(leftW + rightW, '-'))
    for k, v in itemsD.items():
        print(k.ljust(leftW, '.') + str(v).rjust(rightW))

picnicItems = {'bread':4, 'apple':5, 'banana':3, 'drink':10, 'rice':20000}
printPicnic(picnicItems, 12, 6)
printPicnic(picnicItems, 22, 8)

# OUTPUT
---PICNIC ITEMS---
bread.......     4
apple.......     5
banana......     3
drink.......    10
rice........ 20000
---------PICNIC ITEMS---------
bread.................       4
apple.................       5
banana................       3
drink.................      10
rice..................   20000
```

## Removing Whitespace with ```strip()``, ```rstrip()```, & ```lstrip()```

```python
>>> lala.strip()
'Hola'
>>> lala.lstrip()
'Hola     '
>>> lala.rstrip()
'    Hola'
```

Optionally we can use it with an argument:  
```python
>>> lala = 'XXXXHolaXXXX'
>>> lala.strip('XXXX')
'Hola'
>>> lala.strip('XXX')
'Hola'
>>> lala.strip('X')
'Hola'
```

## Copy & Paste with ```pyperclip`` module

```pyperclip`` module has ```copy()``` and ```paste() function to send & receive text from clipboard.  

```python
>>> import pyperclip
>>> pyperclip.copy('hola')
>>> pyperclip.paste()
'hola'
# copy something to clipboard
>>> pyperclip.paste()
'Optionally we can use it with an argument:  \r\n'
>>> 
```


## Project: Password Locker

The command line arguments will be stored in the variable ```sys.argv```   
The first item in the ```sys.argv``` list should always be a string containing the program's filename.  
The second item should be the first command line argument.  
For this program, this argument is the name of the account whose pwd you want.


```python
#! python3
# py.pw - an insecure password locker prog

# 1st step program design & data structure
PASSWORD = { 'email': 'QWERTY123456',
             'bank': 'ytrewq654321',
             'pin': '6969'}

# 2nd step handle cmd line argument
# 3rd copy the right pwd if the variable account exists.

import sys,pyperclip
if len(sys.argv) < 2:
    print('Usage: python py.py [account] - copy account password')
    sys.exit()

account = sys.argv[1]   # first command line arg is the account name

if account in PASSWORD:
    pyperclip.copy(PASSWORD[account])
    print('Password for ' + account + 'copied to clipboard.')
else:
    print('There is no account named ' + account)
```

### In Windows we can create a batch file, ```pw.bat```:
```
@python C:\DATA\Python-Automation-Boring-Stuff\Section6-pw.py %*
@pause
```
```
C:\DATA\Python-Automation-Boring-Stuff>pw pin
Password for pincopied to clipboard.
Press any key to continue . . .

C:\DATA\Python-Automation-Boring-Stuff>6969

## Project: Adding bullets

Program to add bullet points to a really long list from the clipboard

### 1st step: copy & paste from the clipboard
```python
#! python3
# bulletPoointAdder.py  - add bullet points to start of each new line 
# of the text on clipboard

import pyperclip
text = pyperclip.paste()

# TODO: separate lines and add stars

pyperclip.copy(text)
```
### 2nd step: Separate the lines of the text and add the stars


```python
#! python3
# bulletPoointAdder.py  - add bullet points to start of each new line 
# of the text on clipboard

import pyperclip
text = pyperclip.paste()

# Separate the lines and the star 
lines = text.split('\n')
for i in range(len(lines)):     # loop through all indexes in the "lines" list
        lines[] = '* ' + lines[i]    # add start to each sting in "lines" list


pyperclip.copy(text)

```
### 3rd step: Join the modifier lines

```python
#! python3
# bulletPoointAdder.py  - add bullet points to start of each new line 
# of the text on clipboard

import pyperclip
text = pyperclip.paste()

# Separate the lines and the star
lines = text.split('\n')
for i in range(len(lines)):     # loop through all indexes in the "lines" list
    lines[] = "* " + line[i]    # add start to each sting in "lines" list
text = '\n'.join(lines)

pyperclip.copy(text)
````
