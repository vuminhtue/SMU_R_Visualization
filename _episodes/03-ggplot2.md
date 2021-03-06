---
title: "Ploting with ggplot"
teaching: 10
exercises: 0
questions:
- "How to plot in R using ggplot2 package"
objectives:
- "Learn professional plotting tool in R using ggplot2"
- "Learn multiple way to use ggplot2"
keypoints:
- "ggplot2"
---

## What is ggplot
- Grammar of Graphics by Leland Wilkinson
- Written by Hadley Wickham - a grad student at Iowa State
- Third graphic system in for R (along with Base and Lattice)
```r
> install.packages("ggplot2")
> library(ggplot2)
```

## Basic component of ggplot
- A data frame
- aes: aesthetic mappings showing how data are mapped to color, size
- geoms: geometric objects like points, lines, shapes.
- facets: for conditional plots.
- stats: statistical transformations like binning, quanti les, smoothing.
- scales: what scale an aesthetic map uses
- coordinate system
![image](https://user-images.githubusercontent.com/43855029/114095124-0fed0600-988b-11eb-924c-868236195c2a.png)

## Type of ggplot
* Basic qplot
```
- Same as plot in Base plot
- Nicer graphics than Base plot
- Difficult for customize
```
* Advanced ggplot
```
- Flexible with many built-in function
```
