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




