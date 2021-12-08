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
s3 = s1*s2
```

To access index of a Series:

```python
#Using index name
s3['Mustang']

#Using bracket
s3[3]

#Using index location
s3.iloc[3]

#Select subset of Series using filtering
s3[s3>20]
```

Insert an index value

```python
s3['Nothing']=np.nan
s3
```

Catch a null value

```python
s3.isnull()

#Assign null value with some numbers
s3[s3.isnull()]=1
# or
s3.fillna(1)
```

Drop null value (Remove entire row with NaN value)

```python
s3.dropna()
```

Apply function over all index of Series:

```python
s3.apply(np.log10)
```

For longer function, we can use lambda functions.
For example, if there are less than 20 available, we will add the value by 10:

```python
s3.apply(lambda x: x if x>20 else x+10)
```

## Pandas DataFrames
A DataFrame is considered a table of data (similar to a single Excel spreadsheet). It consists of many different pandas Series (as columns) that having the same index.
One should utilize the DataFrame when working with csv, table format.

A sample of DataFrame

```python
year = range(2015,2021)
Series1 = pd.Series([1,2,3,4,5,6],index=year)
Series10 = pd.Series([10,20,30,40,50,60],index=year)
Series100 = pd.Series([100,200,300,400,500,600],index=year)
df = pd.DataFrame([Series1,Series10,Series100],index=['N1','N10','N100'])
```
