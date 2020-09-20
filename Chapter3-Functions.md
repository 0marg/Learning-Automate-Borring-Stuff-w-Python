# 3 Functions

```def``` statement defines a function  
The input to functions are ***arguments***   
The output is the return value    
The parameters are the variables in between the function's parentheses in the def statement   
The return value is specified using the return statement   
Keyword arguments to functions are usually optional   

## Python's Built-in Functions

```python
>>> import random
>>> random.randint(1,10)
4
>>> random.randint(1,10)
10
```

We need to type ```random.``` in front

Alternative form of ```import``` :  
(no need to type random. in front  but not recommended)

```python
>>> from random import *
>>> randint(1,10)
6
```

```python
>>> import sys
>>> sys.exit()
>>> 
```

```python
import sys
print('hello')
sys.exit()
print('bye')
```

To install third party function: https://automatetheboringstuff.com/2e/appendixa/ PyPi

```python
>>> import pyperclip
Traceback (most recent call last):
  File "<pyshell#34>", line 1, in <module>
    import pyperclip
ModuleNotFoundError: No module named 'pyperclip'

> pip.exe install pyperclip
Collecting pyperclip
  Downloading https://files.pythonhosted.org/packages/f6/5b/55866e1cde0f86f5eec59dab5de8a66628cb0d53da74b8dbc15ad8dabda3/pyperclip-1.8.0.tar.gz
Building wheels for collected packages: pyperclip
  Building wheel for pyperclip (setup.py) ... done
  Created wheel for pyperclip: filename=pyperclip-1.8.0-cp37-none-any.whl size=8697 sha256=0d71bf9d71f69c0c88bf6ce0ec75e23860c918582f23484a7cc69a390df93635
  Stored in directory: C:\Users\ogani\AppData\Local\pip\Cache\wheels\b2\ac\0a\b784f0afe26eaf52e88a7e15c7369090deea0354fa1c6fc689
Successfully built pyperclip
Installing collected packages: pyperclip
Successfully installed pyperclip-1.8.0

>>> import pyperclip
>>> pyperclip.copy('hello world')
>>> pyperclip.paste()
'hello world'
```

### Write your own function

```python
def hello(name):
    print('howdy ' + name)
    print('hola ' + name)
    print('hij ' + name )
hello('Alice')
hello('Bob')

###OUTPUT:
howdy Alice
hola Alice
hij Alice
howdy Bob
hola Bob
hij Bob
```

```python
>>> 'Hello has ' + str(len('hello')) + ' letters in in.'
'Hello has 5 letters in in.'
```

### ```return``` keyword

```python
def plusOne(number):
    return number + 1
newNumber = plusOne(4)
print(newNumber)

# OUTPUT:
5
```

### The None value

Every function calls return value; print returns "None"
None return value

```python
>>> 'Hello'
'Hello'
>>> print('Hello')
Hello
>>> None

>>> var = print()
>>> var
>>> var == None
True
```

If a  function does not have a ```return()``` value, the return value defaults to "None" value.

### Keyword arguments and ```print()```

Print automatically adds new line ass the end of the line

```python
# print without argument
print('hello')
print('world')

#  print with end argument
print('hello ', end ="")
print('world')

# print without argument
print('cat', 'dog', 'mouse')

# print with sep argument
print('cat', 'dog', 'mouse', sep='XXX')

# OUTPUT:
hello
world
hello world
cat dog mouse
catXXXdogXXXmouse
```

## Global & Local scopes

```python
var = 22 # global variable
def telors():
    var = 33 # local variable
```

4 important rules:  
1. code in the global scope cannot use any local variables  
2. code in the local scope can access global variables  
3. code in one function's local scope cannot use variables in another local scope  
4. you can use the same name for different variable in different scopes  

### The ```global``` statement

```global``` to change the global variable inside of local variable:  

```python
def nasi():
    telor = 'hello'
    print(telor)
telor = 55
nasi()
print(telor)
# OUTPUT:
hello
55
```
#### VS  

```python
def nasi():
    global telor
    telor = 'hello'
    print(telor)
telor = 55
nasi()
print(telor)
# OUTPUT:
hello
hello
```

## Exception Handling

To skip the program from crashing entirely.

Without exception handling:
```python
def div33by(divideBy):
    return 33 / divideBy
print(div33by(3))
print(div33by(0))
print(div33by(6))

# OUTPUT:
11.0
Traceback (most recent call last):
  File "c:\DATA\GIT\Python-Automation-Boring-Stuff\Section4-handling-error.py", line 5, in <module>
    print(div33by(0))
  File "c:\DATA\GIT\Python-Automation-Boring-Stuff\Section4-handling-error.py", line 2, in div33by
    return 33 / divideBy
ZeroDivisionError: division by zero
```

With exception handling:
```python
def div33by(divideBy):
    try: 
        return 33 / divideBy
    except ZeroDivisionError:
        print('Error: you tried to divide by zero!')
print(div33by(3))
print(div33by(0))
print(div33by(6))

# OUTPUT:
11.0
Error: you tried to divide by zero!
None
5.5
```

Handling error entry:
```python
print('how many cats do you have?')
numCats = input()
try:
    if int(numCats) >= 3:
        print('that is a lot of cats')
    else:
        print('that is not so many cats')
except ValueError:
    print('you did not enter a number')

# OUTPUT:
how many cats do you have?
wee
you did not enter a number
```

### Guess the number program

```python
#this is guessing the number game
import random
print('hello what is your name?')
name = input()
secretNumber = random.randint(1,20)
print('well ' + name + ' guess a number between 1 and 20') # including 1 and 20
# ask the player
for guessTaken in range (1, 7):  # I give you 6 attempts
    print ('take a guess, attempt number ' + str(guessTaken))
    guess = int(input()) # including 1 and 20
    if guess < secretNumber:
        print('your guess is too low')
    elif guess > secretNumber:
        print('your guess is too high')
    else:
        break # this condition is the correct guess
if guess == secretNumber:
    print('good job, you are psychic!  you guess my number in ' + str(guessTaken) + ' guesses')
else:
    print('nope, the number that I was thinking of was ' + str(secretNumber))


# OUTPUT:
hello what is your name?
john
well john guess a number between 1 and 20
take a guess, attempt number 1
10
your guess is too high
take a guess, attempt number 2
5
good job, you are psychic!  you guess my number in 2 guesses
```