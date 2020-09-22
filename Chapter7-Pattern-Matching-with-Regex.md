# 7 Pattern Matching with Regex

## Finding Patterns without Regex 


```isPhoneNumber()``` function to check if a string matches some patterns:  

```python
def isPhoneNumber(text):
    if len(text) !=12:
        return False
    for i in range(0, 3):
        if not text[1].isdecimal():
            return False
    if text[3] != '-':
        return False
    for i in range(4, 7):
        if not text[1].isdecimal():
            return False
    if text[7] != '-':
        return False
    for i in range(8, 12):
        if not text[i].isdecimal():
            return False
    return True

print('555-555-5555 is a phone number')
print(isPhoneNumber('555-555-5555'))
print('lala lala is a phone number')
print(isPhoneNumber('lala lala'))

# OUTPUT:
555-555-5555 is a phone number
True
lala lala is a phone number
False
```

    
Now we can use the function ```if isPhoneNumber()```:  
```pyhon
message = 'call me at 666-666-6666 tomorror or my office at 777-777-7777'
for i in range (len(message)):
    chunk = message[i:i+12]
    if isPhoneNumber(chunk):
        print('Phone number found: ' + chunk)
print('Done')

# OUTPUt
Phone number found: 666-666-6666
Phone number found: 777-777-7777
```

## Finding patter of Text with Regex

### Creating Regex Objects

```python
import re
re.compile()
  .search()
  .group()
```

```python
>>> import re
>>> phoneNumRegex = re.compile(r'\d\d\d-\d\d\d-\d\d\d\d')
>>> mo = phoneNumRegex.search('call me at 666-666-6666 tomorror')
>>> print ('Phone number found: ' + mo.group())
Phone number found: 666-666-6666


