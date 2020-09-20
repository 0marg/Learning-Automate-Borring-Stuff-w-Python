## 1 Python Basics

## Expression: values + operator

value = argument

```python
>>> 2 + 2
4
```

## Data Types

### ints
```python
>>> 4
4
```

### floats 
```python
>>> 4.5
4.5
```

### strings
```python
>>> 'hello'
'hello'
```
Cannot mix the data types!

### Math operators
 (from highest to lowest precedence):

| Operator    | operation     | example | Evaluate to...|
| :----------:|:-------------:|:------:|:---|
| ** | exponent | 2 **3 | 8 |
| % | modulus/reminder | 22 % 8 | 6 |
| // | integer division/floored quotient | 22 // 8 | 2
| / | division | 22 / 8 | 2.75 |
| * | multiplication | 3 * 5 | 35 |
| - | subtraction | 5 -2 | 3 |
| + | addition | 2 + 2 | 4 |

Order of Operations:
1. Parenthesis
2. Multiplication/division
3. addition/subtraction

String concatenation
```python
>>> 'Alice' + 'Bob'
'AliceBob'
```

String Replication:
```python
>>> 'Hola' + '!' * 3
'Hola!!!'
```

## Storing values in Variables

Assignment statement
```python
>>> var = 33
>>> var
33
```

Statement
```python
>>> var = 2 + 2
>>> var = var + 2
>>> var
6
```

### variable names
Cannot use the following as variable name:
* hyphens - 
* spaces
* begin with number
* special characters $ ' 

Useful function:
```python
print()
len()
str()
int()
float()
```