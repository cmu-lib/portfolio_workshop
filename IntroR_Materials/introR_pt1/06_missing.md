---
layout: default
grand_parent: Introduction to R Getting started with R and RStudio
parent: Introduction to R Part 1 
has_children: false
nav_order: 7
title: Missing data
---

## Missing data 

As R was designed to analyze datasets, it includes the concept of missing data (which is uncommon in other programming languages). Missing data are represented in vectors as `NA`.
 
When doing operations on numbers, most functions will return `NA` if the data you are working with include missing values. This feature makes it harder to overlook the cases where you are dealing with missing data. You can add the argument `na.rm=TRUE` to calculate the result while ignoring the missing values. 

```
rooms <-c(2, 1, 1, NA, 4) 
mean(rooms) 
[1] NA 
max(rooms) 
[1] NA 
mean(rooms, na.rm = TRUE) 
[1] 2 
max(rooms, na.rm = TRUE) 
[1] 4 
```


If your data include missing values, you may want to become familiar with the functions `is.na()`, `na.omit()`, and `complete.cases()`. See below for examples. 

```
## Extract those elements which are not missing values. 
rooms[!is.na(rooms)] 
[1] 2 1 1 4 
## Count the number of missing values. 
sum(is.na(rooms)) 
[1] 1 
## Returns the object with incomplete cases removed. The returned object is an atomic vector of type `"numeric"` (or `"double"`). 
na.omit(rooms) 
[1] 2 1 1 4 
attr(,"na.action") 
[1] 4 
attr(,"class") 
[1] "omit" 
## Extract those elements which are complete cases. The returned object is an atomic vector of type `"numeric"` (or `"double"`). 
rooms[complete.cases(rooms)] 
[1] 2 1 1 4 
```

#### Exercise 
---
1. Using this vector of `rooms`, create a new vector with the `NA`s removed. 
```
rooms <-c(1, 2, 1, 1, NA, 3, 1, 3, 2, 1, 1, 8, 3, 1, NA, 1) 
```
2. Use the function `median()` to calculate the median of the `rooms` vector. 

3. Use R to figure out how many households in the set use more than 2 rooms for sleeping. 



