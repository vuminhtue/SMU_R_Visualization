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
- "Violin plot"
---

## Boxplot

Here I am plotting the boxplot of highway (hwy) fuel consumption (mpg) for each manufacturer.

```r
ggplot(mpg,aes(x=manufacturer,y=hwy,
               fill=factor(manufacturer)))+
  geom_boxplot()+
  geom_jitter()+
  labs(title="Boxplot for Hwy per manufacturer",x="Manufacturer",y="Highway milage")+
  theme_bw()+coord_flip()+
  theme(legend.position = "none")
```
![image](https://user-images.githubusercontent.com/43855029/114114879-c19e2e00-98af-11eb-8ce8-000f14ac24ae.png)

### Violin plot
```r
g <- ggplot(mpg, aes(class, cty))
g + geom_violin(aes(fill=class)) + 
  labs(title="Violin plot", 
       subtitle="City Mileage vs Class of vehicle",
       caption="Source: mpg",
       x="Class of Vehicle",
       y="City Mileage")
```
![image](https://user-images.githubusercontent.com/43855029/114114954-e7c3ce00-98af-11eb-8040-4dbb0800b5e7.png)
