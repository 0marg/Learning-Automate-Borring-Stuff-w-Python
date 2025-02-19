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

4 easy steps:  

1. import the regex module: ```1. import re```
2. create teh Regex object: ```re.compile()```
3. pass the string you want to search: ```XXXX.search()```
4. call the match object: ```mo.group()```
```

```python
>>> import re
>>> phoneNumRegex = re.compile(r'\d\d\d-\d\d\d-\d\d\d\d')
>>> mo = phoneNumRegex.search('call me at 666-666-6666 tomorrow or my office at 777-777-7777')
>>> print ('Phone number found: ' + mo.group())
Phone number found: 666-666-6666
```
Note: Search only display the first found phone number, not the second number!

## More Pattern Matching with Regex

### Grouping with Parentheses

Adding parentheses will create *group* in the regex: (\d\d\d)-(\d\d\d-\d\d\d\d)

```python
>>> import re
>>> phoneNumRegex = re.compile(r'(\d\d\d)-(\d\d\d-\d\d\d\d)')
>>> mo = phoneNumRegex.search('call me at 666-666-6666 tomorrow')
>>> mo.group(1)
'666'
>>> mo.group(2)
'666-6666'
>>> mo.group(0)
'666-666-6666'
>>> mo.group()
'666-666-6666'
```

if you want to retrieve all the groups at once, use ```groups()```:  
```python
>>> mo.groups()
('666', '666-6666')
>>> areaCode, mainNumber = mo.groups()
>>> print(areaCode)
666
>>> print(mainNumber)
666-6666
```

```mo.groups()``` returns tuple of multiple values

parentheses has special meeting in regex: use ```\(``` :  
```python
>>> import re
>>> phoneNumRegex = re.compile(r'(\d\d\d)-(\d\d\d-\d\d\d\d)')
>>> mo = phoneNumRegex.search('call me at 666-666-6666 tomorrow')
>>> mo.groups()
('666', '666-6666')
>>> areaCode,mainNumber = mo.groups()
>>> print(areaCode)
666
>>> print(mainNumber)
666-6666
>>> 
```

## Matching Multiple Groups with the pipe |
The first occurrence of matching text will be returned as the Match object.
```python
>>> animalRegex = re.compile(r'Dog|Cat')
>>> mo1 = animalRegex.search('we are living with Cat and Dog.')
>>> mo1.group()
'Cat'
```

```python
>>> batRegex = re.compile(r'Bat(man|mobile|copter|bat)')
>>> mo = batRegex.search('Batmobile lost a wheel')
>>> mo.group()
'Batmobile'
>>> mo.group(1)
'mobile'
```
---
| quantifier | matching |
|:----------:|:---------|
| ? | optional, zero or one |
| * | zero or more |
| + | one or more |
| {} | repetitive |
| {n} | exactly n times |
| {min,} | min or more times |
| {min,max} | at least min times, but not more than max time |
---

## ? : Optional, zero or one matching 

```pyton
>>> batRegex = re.compile(r'Bat(wo)?man')
>>> mo1 = batRegex.search('Robin talks to Batwoman')
>>> mo1.group()
'Batwoman'
>>> mo2 = batRegex.search('Robin rides with Batman')
>>> mo2.group()
'Batman'
```

## * : zero or more matching

```python
p()
'Batman'
>>> batRegex = re.compile(r'Bat(wo)*man')
>>> mo1 = batRegex.search('Robin rides with Batman')
>>> mo1.group()
'Batman'
>>> mo2 = batRegex.search('Robin talk to Batwoman')
>>> mo2.group()
'Batwoman'
>>> mo3 = batRegex.search('lala Batwowowowowoman')
>>> mo3.group()
'Batwowowowowoman'
```

## + : one or more matching

## {}: specific repetition matching

```python
>>> import re
>>> haRegex = re.compile(r'(Ha){3}')
>>> mo1 = haRegex.search('hahaha')
>>> mo1.group()
Traceback (most recent call last):
  File "<pyshell#4>", line 1, in <module>
    mo1.group()
AttributeError: 'NoneType' object has no attribute 'group'
>>> mo1 = haRegex.search('HaHaHa')
>>> mo1.group()
'HaHaHa'
>>> mo2 =haRegex.search('Ha')
>>> mo2.group()
Traceback (most recent call last):
  File "<pyshell#8>", line 1, in <module>
    mo2.group()
AttributeError: 'NoneType' object has no attribute 'group'
>>> mo2 == None
True
```
## Greedy and Nongreedy Matching









