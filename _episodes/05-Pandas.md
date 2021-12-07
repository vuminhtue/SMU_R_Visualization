---
title: "Introduction to Pandas"
teaching: 20
exercises: 0
questions:
- "What is Pandas"
- "DataFrame in Python"
- "How to read text/csv file"
objectives:
- "Working with Data Frame"
- "Create data frame"
- "Import and export data frame"
- "Working with text/csv files"
keypoints:
- "Working with csv input data"
---

## Pandas
Pandas[https://pandas.pydata.org/] stands for "Python and data analysis" and "panel data".

- Pandas is an open source Python library specialize in data structures and operations for the manipulation of numerical tables and time series

- Pandas is a fast, powerful, flexible and easy to use open source data analysis and manipulation tool, it is built on top of the Python programming language.

- To use pandas, one needs to install and import it into the library

```python
!pip install pandas
import pandas as pd
```

There are 2 important data structure in pandas: (1) Series and (2) Data Frame

## Pandas Series

```python
s1 = pd.Series([0,1,2,3,4,5])
```

Pandas Series is a multidimensional numpy array with array index on the first column and array value on the second column.
To retrieve index and its values:

```python
s1.index
s1.values
type(s1.index)
type(s1.values)
```

The index can be changed for more meaning full Series:

```python
s1.index=['Tiger','Cow','Polar Bear','Mustang','Lion','Dragon']
s1
```

Or a new pandas Series can be created using index:

```python
s2 = pd.Series([1,2,3,4,5,6],index=s1.index)
s2
```

One can add the 2 Series if they have similar index:

```python
s3 = s1+s2
```

To access index of a Series:

```python
s3['Mustang']
```
