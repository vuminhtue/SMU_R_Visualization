---
title: "All other Seaborn plots"
teaching: 20
exercises: 0
questions:
objectives:
keypoints:
---

The previous episodes introduced some of the very basic plotting command for Matplotlib as well as Seaborns.
However, there are many other beautiful plots by Seaborn (and more convenient). Some of those can be introduced below:

## 1D Density plot:

```python
sns.FacetGrid(mtcars, hue="cyl", size=4, aspect=1).map(sns.kdeplot, "drat", shade=True, ax=ax[1])
sn
```
