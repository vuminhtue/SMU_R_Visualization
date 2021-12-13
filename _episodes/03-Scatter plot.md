---
title: "Scatter plot"
teaching: 20
exercises: 0
questions:
objectives:
- "Learn how to plot a nice scatter plot in matplotlib"
keypoints:
- "matplotlib, scatter plot"
---

## Scatter plot

_Syntax_

```python
plt.scatter(X, Y)
```

## Let's load some Covid-19 data from Kaggle and we will start PLOTTING !!!

```python
import pandas as pd
df = pd.read_csv('https://raw.githubusercontent.com/vuminhtue/SMU_Python_Basic/master/data/1-1-21%20US%20covid19.csv')
df = df.set_index('State/Territory')
df.head()
```

![image](https://user-images.githubusercontent.com/43855029/145853330-7f3fc82f-8d9b-4a4a-942c-9f980d9299cf.png)

Now let's move on to other type of plot

Plot a scatter plot with X axis for Total Cases and Y axis for Total Deaths

```python
%matplotlib notebook
X = df['Total Cases']
Y = df['Total Deaths']

plt.scatter(X,Y,c = "green", s = 30, marker='s')
plt.title("USA Covid19: Total Cases vs Total Death in all states")
plt.xlabel('Total Number of Cases')
plt.ylabel('Total Number of Deaths')
```

![image](https://user-images.githubusercontent.com/43855029/145853385-60fbd0e4-1ab6-4075-872c-ba003a757c60.png)

If we want to have a more detailed scatter plot with different regions, we introduce the color layer and corresponding legend:

```python
%matplotlib notebook
X = df['Total Cases']
Y = df['Total Deaths']
C = df['State Region'].factorize()

s=plt.scatter(X,Y,c = C[0], s = 30, marker='s',cmap="Spectral")
plt.legend(s.legend_elements()[0],C[1])

plt.title("USA Covid19: Total Cases vs Total Death in all states")
plt.xlabel('Total Number of Cases')
plt.ylabel('Total Number of Deaths')
```

![image](https://user-images.githubusercontent.com/43855029/145853423-37a65043-c076-43bf-9855-66107e757eda.png)


And it is shorter using seaborn

```python
%matplotlib notebook
import seaborn as sns
X = df['Total Cases']
Y = df['Total Deaths']
Z = df['State Region']
sns.scatterplot(X,Y,hue=Z,data=df)
```

![image](https://user-images.githubusercontent.com/43855029/145853490-aac1c3ce-9c2a-45fa-ad2f-df8f7998a09e.png)

