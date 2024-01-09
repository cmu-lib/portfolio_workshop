---
layout: default
grand_parent: Introduction to R: Getting started with R and RStudio
parent: Introduction to R Part 1
has_children: false
nav_order: 3
title: Creating objects in R
---

## Creating objects in R 
You can get output from R simply by typing math in the console: 

```
3+5 
[1] 8 
12 / 7 
[1] 1.714286 
```

However, to do useful and interesting things, we need to assign values to objects. To create an object, we need to give it a name followed by the assignment operator `<-`, and the value we want to give it: 

```
area_hectares <-1.0 
```

`<-` is the assignment operator. It assigns values on the right to objects on the left. So, after executing `x <-3`, the value of `x` is `3`. The arrow can be read as `3` goes into `x`. 

**Note:** You can also use `=` for assignments, but not in every context. Because of the slight differences in syntax, it is good practice to always use `<-` for assignments. More generally we prefer the `<-` syntax over `=` because it increases the readability of the code.    

Objects can be given any name such as `x`, `current_temperature`, or `subject_id`. However, there are some general rules and best practices concerning naming. 

### Naming Rules 
* Cannot start with a number (2x is not valid, but x2 is). 
* R is case sensitive (e.g., age is different from Age). 
* There are some names that cannot be used because they are the names of fundamental functions in R (e.g., if, else, for, see [here](https://stat.ethz.ch/R-manual/R-devel/library/base/html/Reserved.html) for a complete list). In general, even if it's allowed, it's best to not use other function names (e.g., `c`, `T`, `mean`, `data`, `df`, `weights`). 


### Naming Best Practices 
* Object names should be explicit and not too long. 
* Use nouns for object names, and verbs for function names. 
* Avoid dots `(.)` within an object name as in `my.dataset`. There are many functions in R with dots in their names for historical reasons, but because dots have a special meaning in R (for methods) and other programming languages, it's best to avoid them. 
* Be consistent in the styling of your code (where you put spaces, how you name objects, etc.). Using a consistent coding style makes your code clearer to read for your future self and your collaborators. 



### Objects vs. variables 

What are known as `objects` in R are known as variables in many other programming languages. Depending on the context, `object` and `variable` can have drastically different meanings. However, in this lesson, the two words are used synonymously. For more information see: [https://cran.r-project.org/doc/manuals/r-release/R-lang.html#Objects](https://cran.r-project.org/doc/manuals/r-release/R-lang.html#Objects).    

When assigning a value to an object, R does not print anything. You can force R to print the value by using parentheses or by typing the object name: 

```
area_hectares <- 1.0 # doesn't print anything 
(area_hectares <-1.0) # putting parentheses around the call prints the value of `area_hectares` 
[1] 1 
area_hectares # and so does typing the name of the object 
[1] 1
```
 
Now that R has `area_hectares` in memory, we can do arithmetic with it. For instance, we may want to convert this area into acres (area in acres is 2.47 times the area in hectares): 

```
2.47 * area_hectares 
[1] 2.47
```
 
We can also change an objectÕs value by assigning it a new one: 

```
area_hectares <-2.5 
2.47 * area_hectares 
[1] 6.175 
```

This means that assigning a value to one object does not change the values of other objects. For example, let's store the plot's area in acres in a new object, `area_acres`: 

```
area_acres <-2.47 * area_hectares 
```

and then change `area_hectares` to 50. 

```
area_hectares <-50 
```

#### Exercise 
---
What do you think is the current content of the object `area_acres`? 123.5 or 6.175? 


