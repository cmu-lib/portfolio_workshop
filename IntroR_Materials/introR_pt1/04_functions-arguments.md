---
layout: default
grand_parent: Introduction to R: Getting started with R and RStudio
parent: Introduction to R Part 1
has_children: false
nav_order: 5
title: Functions and arguments
---


## Functions and their arguments 

Functions are 'canned scripts' that automate more complicated sets of commands including operations assignments, etc. Many functions are predefined, or can be made available by importing R packages (more on that later). 

A function usually gets one or more inputs called arguments. Functions often (but not always) return a value.Atypical example would be the function `sqrt()`. The input (the argument) must be a number, and the return value (in fact, the output) is the square root of that number. Executing a function (i.e., running it) is called *calling* the function. An example of a function call is:

``` 
b <-sqrt(a) 
```

Here, the value of `a` is given to the `sqrt()` function, the `sqrt()` function calculates the square root, and returns the value which is then assigned to the object `b`. This function is very simple, because it takes just one argument.   

The return value of a function need not be numerical (like that of `sqrt()`), and it also does not need to be a single item: it can be a set of things, or even a dataset. We'll see that later when we read data files into R.    

Arguments can be anything -not only numbers or filenames, but also other objects. Exactly what each argument means differs per function, and must be looked up in the documentation (see below). Some functions take arguments which may either be specified by the user, or, if left out, take on a default value: these are called *options*. Options are used to alter the way the function operates, such as whether it ignores certain values, or what symbol to use in a plot. 

Let's try a function that can take multiple arguments: `round()`. 

```
round(3.14159) 
[1] 3 
```

Here, we've called `round()` with just one argument, `3.14159`, and it has returned the value 3. That's because the default is to round to the nearest whole number. If we want more digits we can see how to do that by getting information about the `round` function. We can use `args(round)` or look at the help for this function using `?round`. 

```
args(round) 
function (x, digits = 0) 
NULL 
?round
```
 
We see that if we want a different number of digits, we can type `digits=2` or however many we want. 

```
round(3.14159, digits = 2) 
[1] 3.14 
```

If you provide the arguments in the exact same order as they are defined you don't have to name them: 

```
round(3.14159, 2) 
[1] 3.14 
```

And if you do name the arguments, you can switch their order: 

```
round(digits = 2, x = 3.14159) 
[1] 3.14 
```

It's good practice to put the non-optional arguments (like the number you're rounding) first in your function call, and to specify the names of all optional arguments. If you don't, someone reading your code might have to look up the definition of a function with unfamiliar arguments to understand what you're doing. 

#### Exercise 
---

Type `?round` into the console and then look at the output in the Help pane. What other functions exist that are similar to round? How do you use the `digits` parameter in the round function? 

