## 2 Flow Control

### Boolean values 

#### boolean operators
```python
>>> True
True
>>> False
False
```

#### Comparison operators:
```python
==
!=
<
>
<=
>=
```

```python
>>> 33 == 33
True
>>> 33 == 44
False
>>> 33 != 44
True
```

#### Boolean Operators: and, or, not
```python
>>> True and True
True
>>> True or False
True
>>> not False or False
True

>>> myAge = 26
>>> myPet = 'cat'
>>> myAge > 20 and myPet == 'cat'
True
```

### Elements of Flow Control

#### ```if``` Statement

```python
name = 'Alice'
if name == 'Alice':
    print('Hi Alice')
print('Done')
```

#### ```else``` Statement

```python
password = 'swordfish'
if password == 'swordfish':
    print('access granted')
else:
    print('wrong password')
# OUTPUT: access granted
```

#### ```elif``` Statement

```python
#order of elif MATTERS
name = 'Bob'
age = 3000
if name == 'Alice':
    print('hi Alice')
elif age > 2000:
    print('you\'re pretty old')
elif age > 100:
    print('you\'re nit Alice and you\'re old')
# OUTPUT: you're pretty old
```

```python
print ('Enter a name')
name = input()
if name != '':
    print('thank you for entering a name')
else:
    print('you did not enter name')
```

#### ```bool()``` function
The value 0, 0.0 and empty string are considered Falsey values.

```python
>>> bool(0)
False
>>> bool(33)
True
>>> bool('hello')
True
>>> bool('')
False
```

```python
print ('Enter a name')
name = input()
if name != '':
    print('thank you for entering a name')
else:
    print('you did not enter name')
```

#### ```while``` Loop Statement

```python
name = ''
while name != 'your name':
    print ('pls type your name.')
    name = input()
print ('thank you')
```

```python
>>> while True:
	print('hello')
hello
hello
hello
CTRL-C to break.
```

using ```break```: to immediately exit the loop

```python
name = ''
while True:
    print ('pls type your name.')
    name = input()
    if name == 'your name':
        break
print ('thank you')
```

using ```continue```: go to top again

```python
var = 0
while var < 5:
    var = var + 1
    if var == 3:
        continue
    print('var is ' + str(var))
OUTPUT: 
var is 1
var is 2
var is 4
var is 5
```

Note the continue will go all the way up again:

```python
while True:
    print('who are you?')
    name = input()
    if name != 'Joe':
        continue
    print('hello Joe, what is the password? (it\'s fishy)')
    password = input()
    if password == 'fishy':
        break
print('access granted')

### OUTPUT
# who are you?
# la
# who are you?
# Joe
# hello Joe, what is the password? (it's fishy)
# fish     <--- it goes back up again !!!
# who are you?
# Joe
# hello Joe, what is the password? (it's fishy)
# fishy
# access granted
```

```python
while True:
    print('who are you?')
    name = input()
    if name != 'Joe':
        continue
    print('hello Joe, what is the password? (it\'s fishy)')
    password = input()
    if password == 'fishy':
        print('correct password, not give me the OTP! (it\'s 333)')
        OTP = input()
        if OTP == '333':
           break
print('access granted')

### OUTPUT
# who are you?
# Joe
# hello Joe, what is the password? (it's fishy)
# fishy
# correct password, not give me the OTP! (it's 333)
# 111  <--goes all the way to up again
# who are you?
# Joe
# hello Joe, what is the password? (it's fishy)
# fishy
# correct password, not give me the OTP! (it's 333)
# 333
# access granted
```

Remember: "truthy" and "falsey" values:
when used in condition: 0, 0.0 and '' are considered ```False```, other values are considered ```True```.

```python
name = ''
while not name:
    print('enter your name:')
    name = input()
print('how many guests will you have?')
numOfguess = int(input())
if numOfguess:
    print('be sure to have enough room fo all your guests')
print('done')
### OUTPUT
# enter your name:
# lala
# how many guests will you have?
# 11
# be sure to have enough room fo all your guests
# done
```

### ```for``` loop and the ```range()``` function 

```python
print('my name is')
for i in range(5):
    print('lala five times ' + str(i))
### OUTPUT: 
# my name is
# lala five times 0
# lala five times 1
# lala five times 2
# lala five times 3
# lala five times 4
```

you can use ```break``` and ```continue``` inside for loop

```python
# the sum from 1 to 100
total = 0
for n in range (101):
    total = total + n
print(total)

### OUTPUT:  5050
```

```python
print('my name is')
for i in range (12,15):
    print ('lala three times ' + str(i))

### OUTPUT:  
my name is
lala three times 12
lala three times 13
lala three times 14
```

```python
print('my name is')
for i in range (2, -1, -1):
    print ('lala five times ' + str(i))

### OUTPUT:  
my name is
lala five times 2
lala five times 1
lala five times 0
```

### Equivalent ```while``` loop

```python
print('my name is')
i = 0
while i < 5:
    print('lala five time (' +str(i) + ')')
    i = i + 1

### OUTPUT:
lala five time (0)
lala five time (1)
lala five time (2)
lala five time (3)
lala five time (4)
```

### Importing Modules

```python
import random
for i in range(5):
    print(random.randint(1,10))
### OUTPUT:
4
2
6
5
2
```

An alternative method of ```import``` using ```from```:

using ```from``` xxx ```import``` *  
ex: ```from random import *```

But you can also import selected function, which is more controlled:

```python
# randrange ([start,] stop [,step])
from random import randrange
for i in range(3):            
    print (randrange(3, 13, 3))
```


