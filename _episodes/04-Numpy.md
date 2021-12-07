---
title: "Introduction to Numpy"
teaching: 20
exercises: 0
questions:
- "What is Numpy"
- "Vector in Python"
- "How to define matrix in Python?"
- "How to manipulate a data frame in Python?"
- "How to read text/csv file"
objectives:
- "Working with Matrix"
- "Create data frame"
- "Import and export data frame"
- "Working with text/csv files"
keypoints:
- "Working with csv input data"
---

## Numpy
Numpy[https://numpy.org/] stands for Numerical Python

- Numpy is an open source Python library used for scientific computing and provides a host of features that allow a Python programmer to work with high-performance arrays and matrices.

- Nearly every scientist working in Python draws on the power of NumPy.

- NumPy brings the computational power of languages like C and Fortran to Python, a language much easier to learn and use. With this power comes simplicity: a solution in NumPy is often clear and elegant.

- To use numpy, just import it to your library

```python
import numpy as np
```

## Numpy array

```python
list2 = [1,2,3,4]
list2_np = np.array(list2)
type(list2_np)
```

Or assign np array directly using:

```python
list3_np = np.array([1,2,3,4])
```

A vector having different objects: `coercion`

```python
list4_np = np.array(list1)
list4_np
```

## Numpy Multidimensional array (matrix)

```python
Mlist = np.array([[1,2,3,4],[5,6,7,8]])
Mlist
Mlist.shape
Mlist[2,4]
```

## Other popular Numpy function

- arange: start, stop, countby

```python
n = np.arange(0, 40, 2) # start at 0 count up by 2, stop before 40
```

- reshape:

```python
n = n.reshape(4, 5) # reshape array to be multidimension array with 4 rows and 4 cols
```

- linspace: evenly spaced numbers using a specified interval.

```python
l = np.linspace(0, 10, 21) # return 21 evenly spaced values from 0 to 10
```

- Dummy matrix with 0 or 1 values:

```python
np.zeros([4,5])
np.ones((4,5))
```

- Matrix with 1 diagonal:

```python
e = np.eye(4)
np.diag(e)
```

- Transpose matrix

```python
n.T
```


- Math function over array:

```python
n.sum()
n.max()
n.argmax()
```

## Merging Matrices
Merging matrices by row and column using `concatenate` with axis (0: row; 1: col)

```python
m <- np.concatenate(n,e,axis=1)
```

## Matrix slicing

```python
m1 = m[2:,:4]
```

If you change the slicing matrix m1, the original matrix m is also changed:

```python
m1[0,1]=100
m
```

In order to avoid this, we should copy data into new matrix:

```python
m1new = m1.copy()
m1new[:] = 100
m
```

## Iterate over array

There are several ways to iterate over multidimensional array

- Iterate by row

```python
for row in n:
    print(row)
```

- Iterate by index

```python
for ind in range(len(n)):
    print(n[ind])
```

- Iterate by row and index

```python
for row,i in enumerate(n):
    print('row', row)
    print('index value', i)
```
