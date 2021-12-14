---
title: "Shapefile and Raster"
teaching: 10
exercises: 0
questions:

objectives:

keypoints:
- "Shapefile"
- "Raster"
---

### Plot Shapefile for geography study
```
Download shape file data [here](https://opendata.arcgis.com/datasets/a21fdb46d23e4ef896f31475217cbb08_1.zip)
Store it in your folder: c:/R/GIS/ in Windows or /user/R/GIS in MacOS
Unzip it and rename all files to `Countries_WGS84.*` under `C:/GIS/`
```
Install additional packages:
```r
install.packages("rgdal")
install.packages("colorspace")
```

Perform plotting
```r
library(rgdal)
library(colorspace)
library(maps)

setwd('c:/R/GIS/')
gfile <- readOGR(dsn="Countries_WGS84.shp")
names(gfile)
gfile$CNTRY_NAME

plot(gfile)
plot(gfile,col=rainbow_hcl(50))
llgridlines(gfile,lty=5)

```
![image](https://user-images.githubusercontent.com/43855029/114115693-4e95b700-98b1-11eb-8f93-0a27c0922e35.png)

### Plot raster
Here we will plot a raster data base using Global land cover data set. The data can be downloaded from [here](http://due.esrin.esa.int/files/Globcover2009_V2.3_Global_.zip).
Unzip and put the raster data to working directory:

```r
install.packages("raster")
```
```r
library(raster)
library(rgdal)

setwd('c:/R/GIS/')
#import raster
Gcover <- raster("GLOBCOVER_L4_200901_200912_V2.3.tif")
#plot raster
plot(Gcover,main="GLobal Land cover")
```
![image](https://user-images.githubusercontent.com/43855029/114116438-b7316380-98b2-11eb-91d0-0ca5a7b2c3d0.png)
