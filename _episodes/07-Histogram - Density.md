---
title: "Histogram plot"
teaching: 20
exercises: 0
questions:
- "What is Histogram plot"
objectives:
- "Learn how to plot histogram using ggplot2"
keypoints:
- "histogram"
---

### Histogram
```r
g <- ggplot(mpg, aes(displ)) + scale_fill_brewer(palette = "Spectral")
g + geom_histogram(aes(fill=class), 
                   bins=10, 
                   col="black", 
                   size=.1) +   # change number of bins
  labs(title="Histogram with Fixed Bins", 
       subtitle="Engine Displacement across Vehicle Classes",
       x="enginer displacement (m)",
       y="Frequency count") 
```
![image](https://user-images.githubusercontent.com/43855029/114115027-0629c980-98b0-11eb-8f8b-2c9bb4c5d6e6.png)

### Density
```r
g <- ggplot(mpg, aes(cty))
g + geom_density(aes(fill=factor(cyl)), alpha=0.8) + 
    labs(title="Density plot", 
         subtitle="City Mileage Grouped by Number of cylinders",
         caption="Source: mpg",
         x="City Mileage",
         fill="# Cylinders")+
    theme_bw()
```
![image](https://user-images.githubusercontent.com/43855029/114115140-47ba7480-98b0-11eb-87c9-922ae8970516.png)

### Density 2D
```r
gg <- ggplot(faithful,aes(x=eruptions,y=waiting))
gg + stat_density_2d(aes(fill=..level..),
                     geom="polygon",color="black")+
     geom_smooth(method="lm",linetype=2,color="red")+
     scale_fill_continuous(low="green",high="red")+
     geom_point() +
     theme_bw()
```
![image](https://user-images.githubusercontent.com/43855029/114115221-63be1600-98b0-11eb-86b5-c0f6f0d8ecff.png)

