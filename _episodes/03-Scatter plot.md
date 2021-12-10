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
