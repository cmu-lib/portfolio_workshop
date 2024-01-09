---
layout: default
grand_parent: Introduction to R: Getting started with R and RStudio
parent: Introduction to R Part 1
has_children: false
nav_order: 4
title: Comments
---

## Comments 
All programming languages allow the programmer to include comments in their code. To do this in R we use the `#` character.Anything to the right of the `#` sign and up to the end of the line is treated as a comment and is ignored by R. You can start lines with comments or include them after any code on the line.

``` 
area_hectares  <- 1.0  #  land  area  in  hectares  
area_acres  <- area_hectares  *  2.47  #  convert  to  acres  
area_acres  #  print  land  area  in  acres.  
[1]  2.47
```
  
#### Exercise 
--- 

Create two variables `my_length` and `my_width` and assign them values. Create a third variable area and give it a value based on the current values of `my_length` and `my_width`. Show that changing the values of either `my_length` and `my_width` does not affect the value of area. 

