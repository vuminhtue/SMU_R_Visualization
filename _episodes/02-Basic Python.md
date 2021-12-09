---
title: "Basic of Matplotlib"
teaching: 5
exercises: 0
questions:
- "how to do basic arithmetics"
- "how to initialize a variable"
- "how to get help"
objectives:
- "Basic Matplotlib"
keypoints:
- "Use Jupyter Notebook as general platform to write and visualize Python code using Matplotlib."
---

## How to display plot in Jupyter Notebook
You can visualize plot in JNotebook using %matplotlib notebook and %matplotlib inline magic commands.

```python
%matplotlib notebook
(%matplotlib inline)

import matplotlib.pyplot as plt
plt.plot(1,2,'*')
```

## More control over plot

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
