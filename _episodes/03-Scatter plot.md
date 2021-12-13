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

## Let's load some dataset and we will start PLOTTING !!!
Here are the fuel consumption for different type of cars in miles per gallon (mpg)

```python
import pandas as pd
df = pd.read_csv('https://raw.githubusercontent.com/vuminhtue/SMU_Python_Visualization/master/data/mpg.csv?token=AKOSZNPVAEY7GPR2PGOWWVDBW55SG')
df.head()
```

![image](https://user-images.githubusercontent.com/43855029/145855346-8e365918-4659-4d14-96d2-6942017aa0cd.png)

Now let's move on to other type of plot

Plot a scatter plot with X axis for Highway (hwy) and Y axis for City (cty) mpg

```python
%matplotlib notebook
plt.scatter(df["hwy"],df["cty"])
plt.title("Highway vs City Fuel Consumption")
plt.xlabel('Highway (mpg)')
plt.ylabel('City (mpg)')
```

![image](https://user-images.githubusercontent.com/43855029/145856301-66baceff-6198-44cc-bff7-99f9364b00a2.png)

We can also control the color "c", size "s" and marker using the following syntax:

```python
plt.scatter(df["hwy"],df["cty"],c="green",s=20,marker="s")
```

If we want to have a more detailed scatter plot, we introduce the color layer and corresponding legend:

```python
%matplotlib notebook
# Sort data by column:
df1 = df.sort_values(by='cyl')

# Compute factor of cylinder data:
C = df1["cyl"].factorize()

# Start ploting with scatter plot:
s = plt.scatter(df1["hwy"],df1["cty"],c=C[0],s=(C[0]+5)**2,cmap="Spectral")

# Ploting annotation & legend:
plt.legend(s.legend_elements()[0],C[1],title="No. cylinder")
plt.title("Highway vs City Fuel Consumption")
plt.xlabel('Highway (mpg)')
plt.ylabel('City (mpg)')
plt.show()
```

![image](https://user-images.githubusercontent.com/43855029/145860699-42d13c55-f289-46d3-b6a4-665b2708cbdd.png)

And it is shorter using seaborn

```python
%matplotlib notebook
ax = sns.scatterplot(x="hwy",y="cty",hue="cyl",size="cyl",data=df,palette="Spectral")
ax.set(xlabel='Highway (mpg)',
       ylabel='City (mpg)',
       title='Highway vs City Fuel Consumption')
```

![image](https://user-images.githubusercontent.com/43855029/145861518-ded72e77-15d1-47b1-ab06-f37513e46198.png)
