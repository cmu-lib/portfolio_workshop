---
layout: default
grand_parent: Introduction to R Getting started with R and RStudio
parent: Introduction to R Part 2
has_children: false
nav_order: 5
title: Data wrangling with dplyr
---

## Data Wrangling with dplyr 


### Learning dplyr 

**dplyr** is a package for making tabular data wrangling easier by using a limited set of functions that can be combined to extract and summarize insights from your data. Like **readr, dplyr** is also part of the **tidyverse**. These packages were loaded in R’s memory when we called `library(tidyverse)` earlier.   

The package **dplyr** provides easy tools for the most common data wrangling tasks. It is built to work directly with data frames. To learn more about **dplyr** after the workshop, you may want to check out [this handy dplyr cheatsheet](https://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf). 

To make sure that everyone is using the same dataset for this lesson, we’ll read again the SAFI dataset that we downloaded earlier. 

```
## load the tidyverse 
library(tidyverse) 
interviews <-read_csv("data/SAFI_clean.csv", na = "NULL") 
## inspect the data 
interviews 
## preview the data 
# View(interviews) 
```

We’re going to learn some of the most common **dplyr** functions: 
* `select()`: subset columns 
* `filter()`: subset rows on conditions 
* `mutate()`: create new columns by using information from other columns 
* `group_by()` and `summarize()`: create summary statistics on grouped data 
* `arrange()`: sort results 
* `count()`: count discrete values 


#### Selecting columns and filtering rows 

To select columns of a data frame, use `select()`. The first argument to this function is the data frame (`interviews`), and the subsequent arguments are the columns to keep, separated by commas.Alternatively, if you are selecting columns adjacent to each other, you can use a `:` to select a range of columns, read as “select columns from __ to __.” 

```
# to select columns throughout the data frame 
select(interviews, village, no_membrs, months_lack_food) 
# to select a series of connected columns 
select(interviews, village:respondent_wall_type)
```
 
To choose rows based on specific criteria, we can use the `filter()` function. The arguments after the data frame specify the condition(s) we want for our final data frame to adhere to (e.g., village name is Chirodzo). We can chain a series of conditions together using commas between each condition.

``` 
# one condition 
filter(interviews, village == "Chirodzo") 
# A tibble: 39 x 14 
key_ID village interview_date no_membrs years_liv respondent_wall… rooms 
<dbl> <chr> <dttm> <dbl> <dbl> <chr> 
<dbl> 
1 8 Chirod… 2016-11-16 00:00:00 12 70 burntbricks 3 
2 9 Chirod… 2016-11-16 00:00:00 8 6 burntbricks 1 
3 10 Chirod… 2016-12-16 00:00:00 12 23 burntbricks 5 
4 34 Chirod… 2016-11-17 00:00:00 8 18 burntbricks 3 
5 35 Chirod… 2016-11-17 00:00:00 5 45 muddaub 1 
6 36 Chirod… 2016-11-17 00:00:00 6 23 sunbricks 1 
7  37  Chirod…  2016-11-17  00:00:00  3  8  burntbricks  1  
8  43  Chirod…  2016-11-17  00:00:00  7  29  muddaub  1  
9  44  Chirod…  2016-11-17  00:00:00  2  6  muddaub  1  
10  45  Chirod…  2016-11-17  00:00:00  9  7  muddaub  1  
#  …  with  29  more  rows,  and  7  more  variables:  memb_assoc <chr>,  
# affect_conflicts <chr>, liv_count <dbl>, items_owned <chr>, no_meals<dbl>, # months_lack_food <chr>, instanceID <chr> 

# multiple conditions 
filter(interviews, village == "Chirodzo", rooms > 1, no_meals > 2) 
# A tibble: 10 x 14 
key_ID village interview_date no_membrs years_liv respondent_wall… rooms 
<dbl> <chr> <dttm> <dbl> <dbl> <chr> <dbl> 1 10 Chirod… 2016-12-16 00:00:00 12 23 burntbricks 5 2 49 Chirod… 2016-11-16 00:00:00 6 26 burntbricks 2 3 52 Chirod… 2016-11-16 00:00:00 11 15 burntbricks 3 4 56 Chirod… 2016-11-16 00:00:00 12 23 burntbricks 2 5 65 Chirod… 2016-11-16 00:00:00 8 20 burntbricks 3 6 66 Chirod… 2016-11-16 00:00:00 10 37 burntbricks 3 7 67 Chirod… 2016-11-16 00:00:00 5 31 burntbricks 2 8 68 Chirod… 2016-11-16 00:00:00 8 52 burntbricks 3 9 199 Chirod… 2017-06-04 00:00:00 7 17 burntbricks 2 
10 200 Chirod… 2017-06-04 00:00:00 8 20 burntbricks 2 
# … with 7 more variables: memb_assoc <chr>, affect_conflicts <chr>, 
# liv_count <dbl>, items_owned <chr>, no_meals <dbl>, months_lack_food<chr>, 
# instanceID <chr> 
```

### Pipes 
What if you want to select and filter at the same time? There are three ways to do this: use intermediate steps, nested functions, or pipes.   
 
With intermediate steps, you create a temporary data frame and use that as input to the next function, like this: 

```
interviews2 <-filter(interviews, village == "Chirodzo") 
interviews_ch <-select(interviews2, village:respondent_wall_type) 
```

This is readable, but can clutter up your workspace with lots of objects that you have to name individually.   

You can also nest functions (i.e. one function inside of another), like this:    

```
interviews_ch <-select(filter(interviews, village == "Chirodzo"), village:respondent_wall_type) 
```

This is handy, but can be difficult to read if too many functions are nested, as R evaluates the expression from the inside out (in this case, filtering, then selecting). 


The last option, pipes, are a recent addition to R. Pipes let you take the output of one function and send it directly to the next, which is useful when you need to do many things to the same dataset. Pipes in R look like `%>%` and are made available via the **magrittr** package, installed automatically with **dplyr**. 

```
interviews %>% 
	filter(village == "Chirodzo") %>% 
	select(village:respondent_wall_type) 
# A tibble: 39 x 5 
village interview_date no_membrs years_liv respondent_wall_type 
<chr> <dttm> <dbl> <dbl> <chr> 
1 Chirodzo 2016-11-16 00:00:00 12 70 burntbricks 
2 Chirodzo 2016-11-16 00:00:00 8 6 burntbricks 
3 Chirodzo 2016-12-16 00:00:00 12 23 burntbricks 
4 Chirodzo 2016-11-17 00:00:00 8 18 burntbricks 
5 Chirodzo 2016-11-17 00:00:00 5 45 muddaub 
6 Chirodzo 2016-11-17 00:00:00 6 23 sunbricks 
7 Chirodzo 2016-11-17 00:00:00 3 8 burntbricks 
8 Chirodzo 2016-11-17 00:00:00 7 29 muddaub 
9 Chirodzo 2016-11-17 00:00:00 2 6 muddaub 
10 Chirodzo 2016-11-17 00:00:00 9 7 muddaub 
# … with 29 more rows 
```

In the above code, we use the pipe to send the `interviews` dataset first through `filter()` to keep rows where `village` is “Chirodzo”, then through `select()` to keep only the `no_membrs` and `years_liv` columns. Since `%>%` takes the object on its left and passes it as the first argument to the function on its right, we don’t need to explicitly include the data frame as an argument to the `filter()` and `select()` functions any more. 

Some may find it helpful to read the pipe like the word “then”. For instance, in the above example, we take the data frame `interviews`, *then* we `filter` for rows with `village == "Chirodzo"`, *then* we `select` columns `no_membrs` and `years_liv`.
 
If we want to create a new object with this smaller version of the data, we can assign it a new name: 

```
interviews_ch <- interviews %>% 
	filter(village == "Chirodzo") %>% 
	select(village:respondent_wall_type)
 
interviews_ch 
# A tibble: 39 x 5 
village interview_date no_membrs years_liv 
respondent_wall_type <chr> <dttm> <dbl> <dbl> <chr> 
1  Chirodzo  2016-11-16  00:00:00  12  70  burntbricks  
2  Chirodzo  2016-11-16  00:00:00  8  6  burntbricks  
3  Chirodzo  2016-12-16  00:00:00  12  23  burntbricks  
4  Chirodzo  2016-11-17  00:00:00  8  18  burntbricks  
5  Chirodzo  2016-11-17  00:00:00  5  45  muddaub  
6  Chirodzo  2016-11-17  00:00:00  6  23  sunbricks  
7  Chirodzo  2016-11-17  00:00:00  3  8  burntbricks  
8  Chirodzo  2016-11-17  00:00:00  7  29  muddaub  
9  Chirodzo  2016-11-17  00:00:00  2  6  muddaub  
10  Chirodzo  2016-11-17  00:00:00  9  7  muddaub  
#  …  with  29  more  rows 
```
 
#### Exercise  
---

Using pipes, subset the `interviews` data to include interviews where respondents were members of an irrigation association (`memb_assoc`) and retain only the columns `affect_conflicts`, `liv_count`, and `no_meals`. 

#### Mutate 
Frequently you’ll want to create new columns based on the values in existing columns, for example to do unit conversions, or to find the ratio of values in two columns. For this we’ll use `mutate()`. 

We might be interested in the ratio of number of household members to rooms used for sleeping 
(i.e. avg number of people per room): 

```
interviews %>% 
	mutate(people_per_room = no_membrs / rooms) 
# A tibble: 131 x 15 
key_ID village interview_date no_membrs years_liv respondent_wall… rooms 
<dbl> <chr> <dttm> <dbl> <dbl> <chr> <dbl> 
1 1 God 2016-11-17 00:00:00 3 4 muddaub 1 
2 1 God 2016-11-17 00:00:00 7 9 muddaub 1 
3 3 God 2016-11-17 00:00:00 10 15 burntbricks 1 
4 4 God 2016-11-17 00:00:00 7 6 burntbricks 1 
5 5 God 2016-11-17 00:00:00 7 40 burntbricks 1 
6 6 God 2016-11-17 00:00:00 3 3 muddaub 
7 7 God 2016-11-17 00:00:00 6 38 muddaub 1 
8 8 Chirod… 2016-11-16 00:00:00 12 70 burntbricks 3 
9 9 Chirod… 2016-11-16 00:00:00 8 6 burntbricks 1 
10 10 Chirod… 2016-12-16 00:00:00 12 23 burntbricks 5 
# … with 121 more rows, and 8 more variables: memb_assoc <chr>, 
# affect_conflicts <chr>, liv_count <dbl>, items_owned <chr>, no_meals <dbl>, 
# months_lack_food <chr>, instanceID <chr>, people_per_room <dbl> 
```

We may be interested in investigating whether being a member of an irrigation association had any effect on the ratio of household members to rooms. To look at this relationship, we will first remove data from our dataset where the respondent didn’t answer the question of whether they were a member of an irrigation association. These cases are recorded as “NULL” in the dataset. 

To remove these cases, we could insert a `filter()` in the chain: 

```
interviews  %>%  
	filter(!is.na(memb_assoc))  %>%  
	mutate(people_per_room  =  no_membrs  / rooms)  
#  A  tibble:  92  x  15  
key_ID village  interview_date  no_membrs  years_liv  
respondent_wall…  rooms  
<dbl>  <chr>  <dttm>  <dbl>  <dbl>  <chr>  
<dbl>  
1  1  God  2016-11-17  00:00:00  7  9  muddaub  
1  
2  7  God  2016-11-17  00:00:00  6  38  muddaub  
1  
3  8  Chirod…  2016-11-16  00:00:00  12  70  burntbricks  
3  
4  9  Chirod…  2016-11-16  00:00:00  8  6  burntbricks  
1  
5  10  Chirod…  2016-12-16  00:00:00  12  23  burntbricks  
5  
6  12  God  2016-11-21  00:00:00  7  20  burntbricks  
3  
7  13  God  2016-11-21  00:00:00  6  8  burntbricks  
1  
8  15  God  2016-11-21  00:00:00  5  30  sunbricks  
2  
9  21  God  2016-11-21  00:00:00  8  20  burntbricks  
1  
10  24  Ruaca  2016-11-21  00:00:00  6  4  burntbricks  
2  

# … with 82 more rows, and 8 more variables: memb_assoc <chr>, 
# affect_conflicts <chr>, liv_count <dbl>, items_owned <chr>, no_meals <dbl>, 
# months_lack_food <chr>, instanceID <chr>, people_per_room <dbl> 
```

The `!` symbol negates the result of the `is.na()` function. Thus, if `is.na()` returns a value of `TRUE` (because the `memb_assoc` is missing), the `!` symbol negates this and says we only want values of `FALSE`, where `memb_assoc` is not missing. 


#### Exercise 
---

Create a new data frame from the `interviews` data that meets the following criteria: contains only the `village` column and a new column called `total_meals` containing a value that is equal to the total number of meals served in the household per day on average (`no_membrs` times `no_meals`). Only the rows where `total_meals` is greater than 20 should be shown in the final data frame. 

*Hint:* think about how the commands should be ordered to produce this data frame! 


#### Split-apply-combine data analysis and the summarize() function 

Many data analysis tasks can be approached using the *split-apply-combine* paradigm: split the data into groups, apply some analysis to each group, and then combine the results. **dplyr** makes this very easy through the use of the `group_by()` function. 

##### The summarize() function 
`group_by()` is often used together with `summarize()`, which collapses each group into a single-row summary of that group. `group_by()` takes as arguments the column names that contain the **categorical** variables for which you want to calculate the summary statistics. So to compute the average household size by village:

``` 
interviews %>% 
	group_by(village) %>% 
	summarize(mean_no_membrs = mean(no_membrs)) 
# A tibble: 3 x 2 
village mean_no_membrs 
* <chr> <dbl> 1 Chirodzo 7.08 
2 God 6.86 
3 Ruaca 7.57 
```

You may also have noticed that the output from these calls doesn’t run off the screen anymore. It’s one of the advantages of `tbl_df` over data frame.   

You can also group by multiple columns: 

```
interviews %>% 
	group_by(village, memb_assoc) %>% 
	summarize(mean_no_membrs = mean(no_membrs)) 
`summarise()` has grouped output by 'village'. You can override using the `.groups` argument. 
# A tibble: 9 x 3 
# Groups: village [3] 
village memb_assoc mean_no_membrs 
<chr> <chr> <dbl> 
1 Chirodzo no 8.06 
2 Chirodzo yes 7.82 
3 Chirodzo <NA> 5.08 
4 God no 7.13 
5 God yes 8 
6 God <NA> 6 
7 Ruaca no 7.18 
8 Ruaca yes 9.5 
9 Ruaca <NA> 6.22 
```

It is sometimes useful to rearrange the result of a query to inspect the values. For instance, we can sort on `mean_no_membrs` to put the group with the smallest household first: 

```
interviews %>% 
	group_by(village, memb_assoc) %>% 
	summarize(mean_no_membrs = mean(no_membrs)) %>% 
	arrange(mean_no_membrs) 
`summarise()` has grouped output by 'village'. 
You can override using the `.groups` argument. 
#  A  tibble:  9  x  3  
#  Groups:  village [3]  
village  memb_assoc  mean_no_membrs  
<chr>  <chr>  <dbl>  
1  Chirodzo  NA  5.08  
2  God  NA  6  
3  Ruaca  NA  6.22  
4  God  no  7.13  
5  Ruaca  no  7.18  
6  Chirodzo  yes  7.82  
7  God  yes  8  
8  Chirodzo  no  8.06  
9  Ruaca  yes  9.5  
```

To sort in descending order, we need to add the `desc()` function. If we want to sort the results by decreasing order of minimum household size: 

```
interviews %>% 
	group_by(village, memb_assoc) %>% 
	summarize(mean_no_membrs = mean(no_membrs)) %>% 
	arrange(desc(mean_no_membrs)) 
`summarise()` has grouped output by 'village'. You can override using the `.groups` argument. 
# A tibble: 9 x 3 
# Groups: village [3] 
village memb_assoc mean_no_membrs 
<chr> <chr> <dbl> 
1 Ruaca yes 9.5 
2 Chirodzo no 8.06 
3 God yes 8 
4 Chirodzo yes 7.82 
5 Ruaca no 7.18 
6 God no 7.13 
7 Ruaca NA 6.22 
8 God NA 6 
9 Chirodzo NA 5.08 
```

##### Counting 
When working with data, we often want to know the number of observations found for each factor or combination of factors. For this task, **dplyr** provides `count()`. For example, if we wanted to count the number of rows of data for each village, we would do: 

```
interviews %>% 
	count(village) 
# A tibble: 3 x 2 
village n 
* <chr> <int> 
1 Chirodzo 39 
2 God 43 
3 Ruaca 49 
```

For convenience, `count()` provides the `sort` argument to get results in decreasing order: 

```
interviews %>% 
	count(village, sort = TRUE) 
# A tibble: 3 x 2 
village n 
<chr> <int> 
1 Ruaca 49 
2 God 43 
3 Chirodzo 39 
```

#### Exercise 
---
1. How many households in the survey have an average of two meals per day? Three meals per day?Are there any other numbers of meals represented? 

2. Use `group_by()` and `summarize()` to find the mean, min, and max number of household members for each village. 

3. What was the largest household interviewed in each month? 
