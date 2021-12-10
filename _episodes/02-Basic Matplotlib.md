---
title: "Basic Plotting system"
teaching: 5
exercises: 0
questions:
- "How many plotting system in Python"
- "How to use Matplotlib & Other"
objectives:
- "Basic Matplotlib"
- "Basic seaborn"
keypoints:
- "Use Jupyter Notebook as general platform to write and visualize Python code using Matplotlib and Seaborn"
---

## Plotting system in Python
There are many different packages providing plotting system for Python.
- The oldest one is Matplotlib, introduced in 2003 and gives you more control over your plots
- Seaborn is an abstraction layer on top of Matplotlib; You can write a shorter code but having a nicer plot than Matplotlib
- Other: Plotly, Bokeh, Altair, Pygal and their discussion can be found [here](https://opensource.com/article/20/4/plot-data-python)

## How to display plot in Jupyter Notebook
You can visualize plot in JNotebook using %matplotlib notebook and %matplotlib inline magic commands.

```python
%matplotlib notebook
(%matplotlib inline)

import matplotlib.pyplot as plt
plt.plot(1,2,'*')
```

## More control over plot using Matplotlib

```python
# Design the plot
plt.figure()

# Start plotting
plt.plot(1,2,'o')
plt.plot(2,3,'*')
plt.plot(3,4,"s")

# Label and Title:
plt.xlabel('X Label')
plt.ylabel('Y Label')
plt.title('Title')

# Get current axes
ax = plt.gca()
#Set axis property to range (0, 5)
ax.axis([0,5,0,5]))
```

## Install and load seaborn

```python
pip install seaborn
```

## Let's load some Covid-19 data from Kaggle and we will start PLOTTING !!!

```python
import pandas as pd
df = pd.read_csv('https://raw.githubusercontent.com/vuminhtue/SMU_Python_Basic/master/data/1-1-21%20US%20covid19.csv')
df = df.set_index('State/Territory')
df.head()
```

Now let's move on to other type of plot
