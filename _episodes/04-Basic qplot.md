---
title: "Ploting with qplot"
teaching: 10
exercises: 0
questions:
- "How to quick plot in R using ggplot2 package"
objectives:
- "Learn professional plotting tool in R using qplot"
- "Learn multiple way to use qplot"
keypoints:
- "ggplot2"
- "qplot"
---

## What is qplot
- qplot stands for quick plot in ggplot2.
- It is similar to basic plot in R but with ggplot 2's standard

In this episode, we gonna learn how to quickly visualize data using qplot

## Basic qplot: Scatter plot
- Plots are made of aes (size, shape, color) and geom (points, lines)
- Look for data in frame (or from parent directory)
```r
qplot(Sepal.Length, Sepal.Width, data=iris)
```
- Add aesthetic (shape, color)
```r
qplot(Sepal.Length, Petal.Length, data=iris,
      color=factor(Species),
      shape=factor(Species)) #aesthetic
```
![image](https://user-images.githubusercontent.com/43855029/114095545-8ab62100-988b-11eb-8383-38d4a0802423.png)
- Add geom (points, lines)
```r
qplot(Sepal.Length, Petal.Length, data=iris,
      geom=c("point","smooth")) #geometry
```
![image](https://user-images.githubusercontent.com/43855029/114095674-b507de80-988b-11eb-8a9f-852ed19ed08a.png)

- Linear Fitting
```r
qplot(Sepal.Length, Petal.Length, data=iris, color=Species,
      geom=c("point","smooth"),method="lm")
```
![image](https://user-images.githubusercontent.com/43855029/114095642-aae5e000-988b-11eb-925b-91336205073d.png)

## Basic qplot: Histogram
```r
qplot(Sepal.Length,fill=Species, data=iris)
qplot(Sepal.Length,data=iris,geom="density")
qplot(Sepal.Length,data=iris,geom="density",
      color=Species)
```
![image](https://user-images.githubusercontent.com/43855029/114096068-3c555200-988c-11eb-849a-1332fcf7c8f5.png)

## Basic qplot: Facets
```r
qplot(Sepal.Length,Petal.Length,facets=.~Species, data=iris)
```
![image](https://user-images.githubusercontent.com/43855029/114096115-4d9e5e80-988c-11eb-8b75-c2a4d88282da.png)

