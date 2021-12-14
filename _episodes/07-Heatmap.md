---
title: "Heatmap"
teaching: 10
exercises: 0
questions:

objectives:

keypoints:
- "Heatmap, Seaborn"
---

## Let's load some time series data from previous example using Jena Climate

```python
import pandas as pd
df = pd.read_csv('https://raw.githubusercontent.com/vuminhtue/SMU_Python_Visualization/master/data/us.csv?token=AKOSZNMCMDFLUIE4C62OVP3BW62LG')
df.head()
# Convert the date column from string to datetime type
df["date"] = pd.to_datetime(df["Date Time"])
df["month"] = df["date"].dt.month
df["year"]  = df["date"].dt.year
```

Create aggregated data (mean monhtly Temperature):

```python
df1 = df.groupby(['year','month'])['T (degC)'].mean().reset_index()
```

Then make a pivot table

```python
df1 = df1.pivot("month","year","T (degC)")
#Drop the last year (nan value)
df1 = df1.drop(2017,axis=1)
```

Plot heatmap

```python
sns.heatmap(df1,annot=True,cmap="rocket_r")
```

![image](https://user-images.githubusercontent.com/43855029/146045085-1a6f86ce-e2fe-4e0b-b6e4-9bac9170306e.png)


