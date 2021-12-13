---
title: "Histogram plot"
teaching: 20
exercises: 0
questions:
- "What is Histogram plot"
objectives:
- "Learn how to plot histogram using Matplotlib and Seaborn"
keypoints:
- "histogram"
---

## Using Matplotlib

Let continue with a histogram plot with the xaxis is Engine Displacement value and the bin value equals to 9.
```python
%matplotlib notebook
plt.hist(df['displ'],bins=9)
plt.title("Histogram of Engine Displacement")
plt.xlabel("Engine Displacement")
plt.ylabel("Frequency count")
```

![image](https://user-images.githubusercontent.com/43855029/145872868-bed4cb4a-4666-45d4-90bb-055bdd8edd07.png)

## Using Seaborn

```python
%matplotlib notebook
ax = sns.histplot(x="displ", bins=9, hue="class", data=df,palette = "bright")
ax.set(xlabel='Engine Displacement',
       ylabel='Frequency Count',
       title='Histogram with fixed bins')
```

![image](https://user-images.githubusercontent.com/43855029/145874657-ae3ca47c-3def-4c98-9479-1cb7c352683e.png)


### Plotting 2 different historgram plot using seaborn.jointplot

Here we will plot the distribution of fuel consumption for Highway and City then plot the scatter plot between them:

```python
sns.jointplot("hwy", "cty",data=df, kind="hex")
```
![image](https://user-images.githubusercontent.com/43855029/145886106-08cb1a25-cd3a-4b37-8116-049d70180b2b.png)


```python
ax = sns.jointplot("hwy", "cty",hue="cyl",data=df,palette="Spectral")
```    

![image](https://user-images.githubusercontent.com/43855029/145885873-615791d6-24b4-4794-9d37-5d08b311340b.png)
