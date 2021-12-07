---
title: "Basic of Python"
teaching: 5
exercises: 0
questions:
- "how to do basic arithmetics"
- "how to initialize a variable"
- "how to get help"
objectives:
- "Python built-in function"
keypoints:
- "Use Jupyter Notebook as general platform to write and run Python code."
- "Python has the usual arithmetic operators and mathematical functions."
---

## Familiar yourself with Jupyter Notebook
- How to request for Jupyter Hub from SMU Open OnDemand platform
- How to use different kernel

## Using Python as calculator
When using Python as a calculator, the order of operations is the same as you
would have learned back in school.

From highest to lowest precedence:

 * Parentheses: `(`, `)`
 * Exponents: `**`
 * Multiply: `*`
 * Divide: `/`
 * Add: `+`
 * Subtract: `-`

```python
a = (1+2)*3-4^5
```

* Other math functions: `sin, cos, log1(), log10()`
For other math functions, we should use numpy library

```python
import numpy as np
np.sin(1)+np.log10(90)
```

## Compare in Python

* `==`: equality
* `!=`: inequality 
* `<`& `<=`: less than & less than or equal to
* `>`& `>=`: more than & more than or equal to

```python
1==1
3!=4
5>4
```

## Assign Variables
- To assign variable in Python, we can use `=` sign

```python
a = 1
```
- To print the variable to console

```python
a
print(a)
```

## Working directory
One important step in R is to define the working directory. It is particularly useful when you are working with files in the working directory and working in Linux environment in Palmetto:

```python
# get current working directory
import os
os.getcwd()
# set working directory
os.chdir('/users/tuev/')
```
## Seeking Help
In order to look for help files for function:

```python
help(numpy.add)
```
