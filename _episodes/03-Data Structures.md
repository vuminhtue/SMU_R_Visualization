---
title: "Data Structures"
teaching: 20
exercises: 0
questions:
- "Class of objects in Python?"
- "Data Type in Python"
- "How many type of number in Python?"
- "Missing values"
- "Subsetting"
objectives:
- "Identify 5 class of objects"
- "Working with List"
- "Type of number in Python"
- "Replace number with subset"
keypoints:
- "Class of objects"
- "Subsetting" 
---

## Classes of objects
In Python, there are 5 main classes of objects:
* str a, b
* float/double: 2.3
* int: 5 
* complex: 2+3j #consists of real and imaginary number
* bool: TRUE/FALSE

```python
str = "string1"
type(str)
a = 5
type(a)
b = 2.4
type(b)
c = 6j ** 3
type(c)
d = 10 < 5
type(d)
```

## Working with string

```python
strcat = 'cat'
strcat + strcat
strcat * 3
strcat + '_loves dog'
```

## Math Operation:

```python
a_quo = a//b #Quotient
a_mod = a%b #Modulo
a_pow = a**b #Power / Exponent 
```

## List
A vector that containts objects from different class is call a `list`. 
In python, a list is created using bracket [ ]

```python
list1 = [str,a,b,c,d]
list1
type(list1)
```

#### A list is mutable 

Append to a list

```python
list1.append(a_quo)
```

Remove from a list

```python
list1.remove(a_quo)
```

Repeat a list 3 times:

```python
list1*3
```

## Tuple
Tuple is a kind of list but created using parenthesis ( ) and has immutable data structure

```python
tup1 = (str, a, b, c, d)
type(tup1)
```

## Subsetting Index for List & Tuple
In Python, the first index starts with 0 and the last one ends with -1

```python
list1[0]
list1[-1]

list1[2:]
list[:2]
list1[2:4]

tup1[0]
```

## Dictionary
Dictionaries are a different way of storing data than lists. They rely on a key and value system as opposed to the order of the entries.
Dictionaries are enclosed in curly braces {}, the key and value are separated by a colon : and entries are separated by commas ,
Values can then be accessed by referencing the key.
Note that finding dictionary values does not go both ways, so using the value to find the key will cause an error.


```python
MyBook = {"The Silmarillion":130115,
          "The Hobbit":95506,
          "The Fellowship of the Ring":187726,
          "The Two Towers":156147,
          "The Return of the King":137037}
          
MyBook["The Two Towers"]         
```
