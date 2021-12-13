---
title: "Line plot"
teaching: 20
exercises: 0
questions:

objectives:

keypoints:
- "Line plot"
---

## Let's load some time series data

```python
import pandas as pd
df = pd.read_csv('https://raw.githubusercontent.com/vuminhtue/SMU_Python_Visualization/master/data/us.csv?token=AKOSZNMCMDFLUIE4C62OVP3BW62LG')
df.head()
```

We have loaded covid 19 cases in US for 2020 and 2021.
The first column contains the date while second and third are positive cases and number of deaths from Covid19

## Using Seasborn

### Plotting with 1 y-axis
Plot using monthly statistics, the middle continuos line is the mean while the shaded represent 25-75 percentile range of the daily data of the month

```python
%matplotlib notebook
df['month'] = pd.to_datetime(df.index).month
sns.lineplot(x="month",y="cases",data=df)
```

### Plotting with 2 y-axes

```python
%matplotlib notebook
df['month'] = pd.to_datetime(df.index).month
sns.lineplot(x="month",y="cases",data=df)
```
