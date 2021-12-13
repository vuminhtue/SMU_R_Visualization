---
title: "Box plots and Violin plots"
teaching: 20
exercises: 0
questions:
- "What is box plot"
objectives:
- "How to draw a nice box plot"
keypoints:
- "Box plot"
---

## Boxplot

Here I am plotting the boxplot of highway (hwy) fuel consumption (mpg) for each manufacturer.
It is more work using Matplotlib compared to Seaborn for this type of plot:

### Using Matplotlib

```python
%matplotlib notebook
data = []
F = df.index.factorize()
for manu in F[1]:
    data.append(df[df.index==manu]["hwy"])

fig, ax = plt.subplots()
    
ax.boxplot(data)
ax.set_xticklabels(F[1],rotation=45)

plt.title("Boxplot for Hwy per manufacturer")
plt.xlabel('Manufacturer')
plt.ylabel('Highway milage')
```

![image](https://user-images.githubusercontent.com/43855029/145869618-d9995d8b-97da-43b6-b3e0-e35d8f8df472.png)

