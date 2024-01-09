---
layout: default
grand_parent: Introduction to R: Getting started with R and RStudio
parent: Introduction to R Part 1
has_children: false
nav_order: 6
title: Working with vectors
---

## Working with vectors

### Vectors and data types 

A vector is the most common and basic data type in R. A vector is composed of a series of values, which can be either numbers or characters. We can assign a series of values to a vector using the `c()` function. 

For example we can create a vector of the number of household members for the households weÕve interviewed and assign it to a new object `hh_members`: 

```
hh_members  <. c(3,  7,  10, 6)  
hh_members  
[1]  3  7  10  6  
```

A vector can also contain characters. For example, we can have a vector of the building material used to construct our interview respondentsÕ walls `(respondent_wall_type)`: 

```
respondent_wall_type <-c("muddaub", "burntbricks", "sunbricks") 
respondent_wall_type 
[1] "muddaub" "burntbricks" "sunbricks" 
```

The quotes around `muddaub`, etc. are essential here. Without the quotes, R will assume there are objects called `muddaub`, `burntbricks` and `sunbricks`. Since these objects don't exist in R's memory, there will be an error message. 

There are many functions that allow you to inspect the content of a vector. length() tells you how many elements are in a particular vector: 

```
length(hh_members) 
[1] 4 
length(respondent_wall_type) 
[1] 3 
```

An important feature of a vector is that all of the elements are the same type of data. The function `class()` indicates the class (the type of element) of an object: 

```
class(hh_members) 
[1] "numeric" 
class(respondent_wall_type) 
[1] "character" 
```


The function `str()` provides an overview of the structure of an object and its elements. It is a useful function when working with large and complex objects: 

```
str(hh_members) 
num [1:4] 3 7 10 6 
str(respondent_wall_type) 
chr [1:3] "muddaub" "burntbricks" "sunbricks"
```
 
You can also use the `c()` function to add other elements to your vector: 

```
possessions <-c("bicycle", "radio", "television") 
possessions <-c(possessions, "mobile_phone") # add to the end of the 
vector 
possessions <-c("car", possessions) # add to the beginning of the 
vector 
possessions 
[1] "car" "bicycle" "radio" "television" "mobile_phone" 
```

In the first line, we take the original vector `possessions`, add the value "`mobile_phone`" to the end of it, and save the result back into `possessions`. Then we add the value "`car`" to the beginning, again saving the result back into `possessions`.   

We can do this over and over again to grow a vector, or assemble a dataset. You can check the type of your vector using the `typeof()` function and inputting your vector as the argument.    

Vectors are one of the many data structures that R uses. Other important ones are lists (`list`), matrices (`matrix`), data frames (`data.frame`), factors (`factor`) and arrays (`array`). 


#### Exercise 1
---
 
We've seen that atomic vectors can be of type `character`, `numeric` (or double), `integer`, and `logical`. But what happens if we try to mix these types in a single vector? 


#### Exercise 2 
---

What will happen in each of these examples? (hint: use `class()` to check the data type of your objects): 

```
num_char <- c(1, 2, 3, "a") 
num_logical <- c(1, 2, 3, TRUE) 
char_logical <- c("a", "b", "c", TRUE) 
tricky <- c(1, 2, 3, "4") 
```

Why do you think it happens? 


#### Exercise 3 
---

How many values in `combined_logical` are "`TRUE`" (as a character) in the following example:

``` 
num_logical <- c(1, 2, 3, TRUE) 
char_logical <- c("a", "b", "c", TRUE) 
combined_logical <- c(num_logical, char_logical) 
```

You've probably noticed that objects of different types get converted into a single, shared type within a vector. In R, we call converting objects from one class into another class coercion. These conversions happen according to a hierarchy, whereby some types get preferentially coerced into other types. 

### Subsetting vectors 

If we want to extract one or several values from a vector, we must provide one or several indices in square brackets. For instance: 

```
respondent_wall_type <- c("muddaub", "burntbricks", "sunbricks") 
respondent_wall_type[2] 
[1] "burntbricks" respondent_wall_type[c(3, 2)] 
[1] "sunbricks" "burntbricks" 
```

We can also repeat the indices to create an object with more elements than the original one: 

```
more_respondent_wall_type <- respondent_wall_type[c(1, 2, 3, 2, 1, 3)] m
ore_respondent_wall_type 
[1] "muddaub" "burntbricks" "sunbricks" "burntbricks" "muddaub" 
[6] "sunbricks" 
```

R indices start at 1. Programming languages like Fortran, MATLAB, Julia, and R start counting at 1, because that's what human beings typically do. Languages in the C family (including C++, Java, Perl, and Python) count from 0 because that's simpler for computers to do. 


### Conditional subsetting 
Another common way of subsetting is by using a logical vector. `TRUE` will select the element with the same index, while `FALSE` will not: 

```
hh_members <- c(3, 7, 10, 6) 
hh_members[c(TRUE, FALSE, TRUE, TRUE)] 
[1] 310 6 
```

Typically, these logical vectors are not typed by hand, but are the output of other functions or logical tests. For instance, if you wanted to select only the values above 5: 

```
hh_members > 5 # will return logicals with TRUE for the indices that meet the condition 
[1] FALSE TRUE TRUE TRUE 
## so we can use this to select only the values above 5 
hh_members[hh_members > 5] 
[1] 710 6 
```

You can combine multiple tests using `&` (both conditions are true,AND) or `|` (at least one of the conditions is true, OR): 

```
hh_members[hh_members < 4 | hh_members > 7] 
[1] 3 10 
hh_members[hh_members >= 7 & hh_members == 3] 
numeric(0) 
```

Here, `<` stands for `less than`, `>` for `greater than`, `>=` for `greater than or equal to`, and `==` for `equal to`. The double equal sign `==` is a test for numerical equality between the left and right hand sides, and should not be confused with the single `=` sign, which performs variable assignment (similar to `<-`).   

A common task is to search for certain strings in a vector. One could use the `or` operator | to test for equality to multiple values, but this can quickly become tedious.   

```
possessions <-c("car", "bicycle", "radio", "television", "mobile_phone") 
possessions[possessions == "car" | possessions == "bicycle"] # returns both car and bicycle 
[1] "car" "bicycle"
```
 
The function `%in%` allows you to test if any of the elements of a search vector (on the left hand side) are found in the target vector (on the right hand side): 

```
possessions %in% c("car", "bicycle") 
[1] TRUE TRUE FALSE FALSE FALSE 
```

Note that the output is the same length as the search vector on the left hand side, because %in% checks whether each element of the search vector is found somewhere in the target vector. Thus, you can use `%in%` to select the elements in the search vector that appear in your target vector:

``` 
possessions %in% c("car", "bicycle", "motorcycle", "truck", "boat", "bus") 
[1] TRUE TRUE FALSE FALSE FALSE 
possessions[possessions %in% c("car", "bicycle", "motorcycle", "truck", "boat", "bus")] 
[1] "car" "bicycle" 
```


