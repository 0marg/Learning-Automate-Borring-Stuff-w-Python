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

```isalpha()```  
```isalnum()```  
```isdecimal()```  
```isspace()```  
```istitle()```  

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

### ```startwith()``` & ```endwith()```





