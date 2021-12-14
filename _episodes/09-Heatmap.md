---
title: "Heatmap"
teaching: 10
exercises: 0
questions:

objectives:

keypoints:
- "Heatmap, Seaborn"
---

## Let's load some time series data from previous example using Jena Climate

```r
data = read.csv('https://raw.githubusercontent.com/vuminhtue/SMU_Python_Visualization/master/data/jena_climate_2009_2016.csv',header = TRUE)
data["date"] = as.POSIXct(data$Date.Time, format="%m.%d.%Y %H:%M:%S")

# Create 2 new columns month and year for data
library(lubridate)
data["month"]=month(data$date)
data["year"]=year(data$date)
```

Create aggregated data (mean monhtly Temperature):

```r
data1 = aggregate(data$T..degC.,by=list(data$year,data$month),FUN=mean)
colnames(data1)=c("Year","Month","T")
```

Remove 2017 

```r
ind <- data1$Year==2017
data1[ind,]=NaN
```

Plot heatmap

```r
ggplot(data1,aes(Year,Month,fill=T))+
  geom_tile()+
  scale_fill_distiller(palette = "RdPu") 
```

![image](https://user-images.githubusercontent.com/43855029/146070305-920b7a0e-4f8c-4131-ad19-361bac00ca4d.png)


