---
title: "Introduction to Visualization with R"
teaching: 5 min
exercises: 0
questions: "How to visualize data in R"
objectives:
- "Basic Introductory of plotting system in R"

keypoints:
- "R Base plotting system and ggplot"
---
## Course content:
- Making exploratory graphs
- Principles of analytic graphics
- Plotting systems and graphics devices in R
- The base, lattice, and ggplot2 plotting systems in R

## Exploratory graph
### Why do we use graphs in data analysis?
- To understand data properties
- To find patterns in data
- To suggest modeling strategies
- To "debug" analyses
- To communicate results

## Ploting System
There are 3 main plotting systems in R:
### The Base plotting system
```
- Start with blank plot and build up the plot
- Plot is just a series of R command
- Flexible
```
###  The Lattice plotting system (using package::lattice)
```
- Plots created using single function call
- Good for putting many plots to screen
- Cannot add to plots once created
```

### The ggplot plotting system (using package::ggplot2)
```
- Similar to Lattice but easier
- Many default mode
- Flexible between Base and Lattice
```
