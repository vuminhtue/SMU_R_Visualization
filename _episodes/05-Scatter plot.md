---
title: "Scatter plot"
teaching: 20
exercises: 0
questions:
objectives:
- "Learn how to plot a nice scatter plot in ggplot2"
keypoints:
- "ggplot2, scatter plot"
---

## Basic component of ggplot

- A data frame
- aes: aesthetic mappings showing how data are mapped to color, size
- geoms: geometric objects like points, lines, shapes.
- facets: for conditional plots.
- stats: statistical transformations like binning, quanti les, smoothing.
- scales: what scale an aesthetic map uses
- coordinate system
![image](https://user-images.githubusercontent.com/43855029/114095124-0fed0600-988b-11eb-924c-868236195c2a.png)

## Layers of ggplot

```r
gp <- ggplot(mpg, aes(hwy, cty))

gp+geom_point(aes(color=cyl))
gp+geom_point(aes(color=factor(cyl)))
gp+geom_point(aes(color=factor(cyl)))+geom_smooth(method="lm")
gp+geom_point(aes(color=factor(cyl)))+geom_smooth(method="lm")
  +facet_grid(.~cyl)
# Save plot to file
ggsave("plot.png",width=5,height=5)
```
![image](https://user-images.githubusercontent.com/43855029/114114690-5a807980-98af-11eb-94b2-ae870139819d.png)

## Scatter plot with full annotation

- Labels: xlab(), ylab(), labs(), ggtitle()
- global annotation: use theme()
- Standard appearance: theme_bw()
```r
gp+geom_point(aes(color=factor(cyl),
              size=factor(cyl)))+
  geom_smooth(method="lm")+
  xlab("Highway miles per gallon")+
  ylab("city miles per gallon")+
  ggtitle("Scatter plot for cty & hwy")+
  xlim(10,40)+ylim(10,40)+
  theme_bw(base_size = 15)
```
![image](https://user-images.githubusercontent.com/43855029/114114812-a16e6f00-98af-11eb-91be-aad368dedb50.png)


Another type of data:

```r
data("midwest")
gg <- ggplot(midwest, aes(x=area, y=poptotal)) + 
  geom_point(aes(col=state, size=popdensity)) + 
  geom_smooth(method="loess", se=F) + 
  xlim(c(0, 0.1)) + 
  ylim(c(0, 500000)) + 
  labs(subtitle="Area Vs Population", 
       y="Population", 
       x="Area", 
       title="Scatterplot", 
       caption = "Source: midwest")
plot(gg)
```
![image](https://user-images.githubusercontent.com/43855029/114115089-278ab580-98b0-11eb-96f4-1d3adc70b511.png)

