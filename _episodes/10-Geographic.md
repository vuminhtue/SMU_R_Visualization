---
title: "Geographical data"
teaching: 10
exercises: 0
questions:

objectives:

keypoints:
- "Geography"
---

## Geographic visualization with ggplot

```r
library(maps)
states <- map_data("state")
ggplot(data = states)+
  geom_polygon(aes(x=long,y=lat,fill=region),
               color="black")+
  coord_fixed(1.3)+
  guides(fill=FALSE)
```
![image](https://user-images.githubusercontent.com/43855029/114115281-84866b80-98b0-11eb-9706-0b07e1472a54.png)

```r
counties <- map_data("county")
SC_counties <- subset(counties,region == "south carolina")
ggplot(data = SC_counties)+
  geom_polygon(aes(x=long,y=lat,fill=subregion),
               color="black")+
  coord_fixed(1.3)+
  guides(fill=FALSE)
```
![image](https://user-images.githubusercontent.com/43855029/114115313-9700a500-98b0-11eb-8771-58631bdc3e54.png)

```r
some.eu.countries <- c(
  "Portugal", "Spain", "France", "Switzerland", "Germany",
  "Austria", "Belgium", "UK", "Netherlands",
  "Denmark", "Poland", "Italy", 
  "Croatia", "Slovenia", "Hungary", "Slovakia",
  "Czech republic"
)
# Retrievethe map data
some.eu.maps <- map_data("world", region = some.eu.countries)

ggplot(some.eu.maps, aes(x = long, y = lat)) +
  geom_polygon(aes( group = group, fill = region))+
  scale_fill_viridis_d()+
  theme_void()+
  theme(legend.position = "none")
```

![image](https://user-images.githubusercontent.com/43855029/122972677-6633f600-d35e-11eb-9c3c-4b90db22b25e.png)

