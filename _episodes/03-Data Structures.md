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
A vector that containts objects from different class is call a `list`
In python, a list is created using bracket [ ]

### A list

```python
list1 = [str,a,b,c,d]
list1
type(list1)
```

### Appending/Remove
Append to a list

```python
list1.append(a_quo)
```

Removing from a list

```python
list1.remove(a_quo)
```


## Random Number & seed
Create random numeric numbers using runif
```r
runif(1)
runif(3)
runif(2,10,20)
```

Create random integer numbers using sample
```r
sample(12,5)
sample(12)
sample(letters,4)
```

### Introduction to `seed`
Set the seed of R's random number generator, which is useful for creating simulations or random objects that can be reproduced.
```r
set.seed(1234)
runif(3)
```

## Missing values
In order to test the missing values or bad values NaN, NA, Inf use some math operations:
* is.na() test NA value
* is.nan() test NaN value
* is.infinite() test Inf value
* NaN is NA but the reverse is false
```r
v <- c(TRUE, 6, 1/0,NA, NaN,-6/0)
v
is.na(v)
is.nan(v)
is.infinite(v)
```

## Subsetting

In order to extract the necessary information, subsetting is used.
In R, subsetting is represented by bracket: `[]`

```r
str <- c("a", "b","c","d")
str
# Find the subset with index 1 for str:
str[1]
# Find the subset with index 2:4 for str:
str[2:4]
```

**Subsetting with List**
```r
list1 <- list(l1=str,l2=4:6)
list1
# Use $ to call a variable name
list1$l1[3]
```

**Subsetting matrix**
```r
m <- matrix(1:12,nrow=3,ncol=4)
m
m[2,3]
```
Subsetting by row or column:
```r
m[2,]
m[,4]
```

**Subsetting `NA/NaN` value**
```r
a <- c(1:5,NaN,TRUE)
a
# Find the location of *NaN* value using `is.nan()` function
ind <- is.nan(a)
ind
# Subset with location of *NaN* value
a[ind]
a[is.nan(a)]
# Subset with location of `Not NaN` values using `!`
a[!ind]
```



