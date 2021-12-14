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
# Convert the date column from string to datetime type
df["date"] = pd.to_datetime(df["date"])
```

We have loaded covid 19 cases in US for 2020 and 2021.
The first column contains the date while second and third are positive cases and number of deaths from Covid19

## Using Matplotlib

```python
%matplotlib notebook
plt.plot(df["date"],df["cases"]/10**6)
plt.title("Covid 19 cases in US")
plt.xlabel("Time")
plt.ylabel("Cases (millions)")
plt.xticks(rotation=45)
```

![image](https://user-images.githubusercontent.com/43855029/146029503-5a3fdc08-8bad-455e-b34b-c55073a81613.png)

Using 2 different axes:

```python
%matplotlib notebook

fig, ax1 = plt.subplots()

ax1.plot(df["date"],df["cases"]/10**6)
ax1.set_title("Covid 19 cases in US")
ax1.set_xlabel("Time")
ax1.set_ylabel("Cases (millions)")
plt.xticks(rotation=45)

ax2 = ax1.twinx()
ax2.plot(df["date"],df["deaths"]/10**3,color="red",linestyle="dashed")
ax2.set_ylabel("Deaths (thousands)",color="red")
```

![image](https://user-images.githubusercontent.com/43855029/146030659-c1eb6210-155a-422c-b058-57a5f6c0e9c9.png)


## Using Seasborn

For seaborn, one can aggregate the plot

First create the separate column for month and year

```python
df['month'] = df.date.dt.month
df['year'] = df.date.dt.year
```

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
