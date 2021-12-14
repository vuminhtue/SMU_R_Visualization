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
