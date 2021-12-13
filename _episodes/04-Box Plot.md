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

### Using Seaborn

For this type of plot, Seaborn provides better and faster method of plotting:

```python
%matplotlib notebook
import seaborn as sns
ax = sns.boxplot(x="hwy",y="manufacturer",data=df)
ax = sns.stripplot(x="hwy",y="manufacturer",data=df,color="black")
ax.set(ylabel='Manufacturer',
       xlabel='Highway milage',
       title='Boxplot for Hwy per manufacturer')
ax.grid()       
```

![image](https://user-images.githubusercontent.com/43855029/145871545-2ac9c158-b6e1-4305-9152-919e5f12dfe5.png)

#### Similarly, we can use the same technique for violin plot:

```python
%matplotlib notebook
import seaborn as sns
ax = sns.violinplot(x="class",y="cty",data=df)
ax.set(xlabel='Class of Vehicle',
       ylabel='City mileage',
       title='Violin plot for City mileage with Class of Vehicle')
ax.grid()
```

![image](https://user-images.githubusercontent.com/43855029/145871965-d2e80d65-82a9-4c38-ac89-03bfc68acf54.png)

