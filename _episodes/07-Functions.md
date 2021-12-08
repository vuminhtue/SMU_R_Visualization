---
title: "Function"
teaching: 10
exercises: 0
questions:
- "How to write function in Python?"
- "How can I use the function from packages"
objectives:
- "Define function"
- "Learn to create `nested` function"
- "Return value(s) from function"
- "Check argument conditions with `stopifnot()` function"
-keypoints:
- "Use `function` to define a new function in Python"
- "Use parameter to pass value to function"
- "Load function into program using `import`"
---

A function is a set of scripts organized together to carry out a specific task. Writing efficient functions is an important skill that can significantly improve the productivity of data scientists and data science solutions. In this guide, you will learn the basics of writing a function and the types of functions, which will enable you perform analytical tasks more efficiently.

## Using custom functions

There are several in-built functions in Python that can be used to perform analytical tasks, for example: `mean, min, max, quantile,summary`. Function in python (numpy, pandas) is normally called via "**.**":


```python
a = np.arange(1,5)
a.mean()

b = np.Series(a)
b.max()
```

## Using User-Define a function without arg(ument):
_Syntax:_

```python
def function_name():
    do some stuff     
```

_Example:_

```python
def callme():
    print('Hello')
```

## Using User-Define a function with 1 arg(ument)
_Syntax:_

```python
def function_name(arg):
    do function with argument
    return output
```

_Example:_

```python
def squareroot1(a):
    a=a+1
    return a**0.5

squareroot(49)
```

## Using User-Define a function with 2 or more arg(uments)
_Syntax:_

```python
f = function(arg1,arg2):
    do function with arg1 & arg2
```

_Example:_

```python
def addtwo(a,b):
    return a+b
}
addtwo(1,2)
```

## Return list of (more) values from function
_Syntax:_

```python
f = function(args):
    do function with args
    out1 <- do1
    out2 <- do2  
    output <- list(out1=out1,out2=out2)
```

_Example:_

```python
def sqsum(a):
    sq = a**0.5
    sum = a+sq
    return sq,sum
    
sqsum(49)
```

## Nested function
In complex data science use cases, we may have to work on nested functions, which contain functions within a function.
For example in the covid dataset, we would like to find the max number of Total Cases with South Region and the associated State:

```python
# Step 1: find the state in South region
ind1 = df['State Region']=='South'
# Step 2: find the Total Cases with respected to South region
ind2 = df['Total Cases'][ind1]
# Step 3: compute the max
ind2.max()
# Step 4: Find the corresponding state with max number of Total Case in the South:
ind2.idxmax()
```

All the steps can be nested into one command line for experience user:

```python
df['Total Cases'][df['State Region']=='South'].max()
df['Total Cases'][df['State Region']=='South'].idxmax()
```
