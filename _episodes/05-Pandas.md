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
ax = sns.histplot(x="displ", hue="class", data=df,palette = "bright")
ax.set(xlabel='Engine Displacement',
       ylabel='Frequency Count',
       title='Histogram with fixed bins')
```

![image](https://user-images.githubusercontent.com/43855029/145874422-2b602d16-057b-4a20-9f5b-76e30ae775b0.png)


