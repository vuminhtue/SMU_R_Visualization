---
title: "Basic Plotting system"
teaching: 5
exercises: 0
questions:
- "How many plotting system in Python"
- "How to use Matplotlib & Seaborn"
objectives:
- "Basic Matplotlib"
- "Basic Seaborn"
keypoints:
- "Use Jupyter Notebook as general platform to write and visualize Python code using Matplotlib and Seaborn"
---

## Plotting system in Python
There are many different packages providing plotting system for Python.
- The oldest one is Matplotlib, introduced in 2003 and gives you more control over your plots
- Seaborn is an abstraction layer on top of Matplotlib; You can write a shorter code but having a nicer plot than Matplotlib. Seaborn can be compared to ggplot2 in R.
- Other: Plotly, Bokeh, Altair, Pygal and their discussion can be found [here](https://opensource.com/article/20/4/plot-data-python)

## How to display plot in Jupyter Notebook
You can visualize plot in JNotebook using %matplotlib notebook and %matplotlib inline magic commands.

```python
%matplotlib notebook
(%matplotlib inline)

import matplotlib.pyplot as plt
plt.plot(1,2,'*')
```

![image](https://user-images.githubusercontent.com/43855029/145853114-9798e00b-3bc9-43dd-b131-84b150b9149f.png)


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

![image](https://user-images.githubusercontent.com/43855029/145853020-a7a44ca1-040f-4333-bd4d-00004e71b084.png)


## Subplot in Matplotlib

Very similar to Matlab, one just need to insert the plot number using subplot command:

```python
plt.subplot(2,2,1)
plt.plot(1,2,'o')
plt.plot(2,3,'*')
plt.plot(3,4,"s")

plt.subplot(2,2,2)
plt.plot(1,2,'o')
plt.plot(2,3,'*')
plt.plot(3,4,"s")

plt.subplot(2,2,3)
plt.plot(1,2,'o')
plt.plot(2,3,'*')
plt.plot(3,4,"s")

plt.subplot(2,2,4)
plt.plot(1,2,'o')
plt.plot(2,3,'*')
plt.plot(3,4,"s")
```

![image](https://user-images.githubusercontent.com/43855029/145853035-f95fc8f1-072d-4808-83d2-1e3fed8fd306.png)


## Install and import seaborn

```python
pip install seaborn
```

