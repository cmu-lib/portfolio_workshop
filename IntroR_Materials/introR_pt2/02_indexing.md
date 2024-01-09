---
layout: default
grand_parent: Introduction to R Getting started with R and RStudio
parent: Introduction to R Part 2
has_children: false
nav_order: 3
title: Indexing and subsetting dataframes
---

## Indexing and subsetting data frames 

Our `interviews` data frame has rows and columns (it has 2 dimensions). In practice, we may not need the entire data frame. For instance, we may only be interested in a subset of the observations (the rows) or a particular set of variables (the columns). If we want to extract some specific data from it, we need to specify the “coordinates” we want from it. Row numbers come first, followed by column numbers. 


### Tip
--- 
Indexing a tibble with `[` or `[[` or `$` always results in a tibble. However, note this is not true in general for data frames, so be careful! Different ways of specifying these coordinates can lead to results with different classes. 

```
## first element in the first column of the data frame (as a data.frame) 
interviews[1, 1] # A tibble: 1 x 1 
key_ID 
<dbl> 
1   	1 

## first element in the 6th column (as a data.frame) 
interviews[1, 6] 
# A tibble: 1 x 1 
respondent_wall_type 
<chr> 
1 muddaub 

## first column of the data frame (as a vector) 
interviews[[1]] 
[1]  1  1  3  4  5  6  7  8  9  10  11  12  13  14  15  16  17  18  
[19]  19  20  21  22  23  24  25  26  27  28  29  30  31  32  33  34  35  36  
[37]  37  38  39  40  41  42  43  44  45  46  47  48  49  50  51  52  21  54  
[55]  55  56  57  58  59  60  61  62  63  64  65  66  67  68  69  70  71  127  
[73] 133 152 153 155 178  177  180  181 182 186  187  195  196  197  198  201  202  72  
[91]  73  76  83  85  89  101  103  102  78  80  104  105  106  109  110  113  118  125  
[109] 119 115 108 116 117 144 143 150 159 160 165 166 167 174 175 189 191 192 
[127] 126 193 194 199 200 

## first column of the data frame (as a data.frame) 
interviews[1] 
# A tibble: 131 x 1 
key_ID 
<dbl>
1	1 
2	1 
3	3 
4	4 
5	5 
6	6 
7	7 
8	8 
9	9 
10 	10 
# … with 121 more rows 

## first three elements in the 7th column (as a data.frame) 
interviews[1:3, 7] 

# A tibble: 3 x 1 
rooms 
<dbl> 
1	1 
2	1 
3	1 

## the 3rd row of the data frame (as a data.frame) 
interviews[3, ] 
# A tibble: 1 x 14 
key_ID village interview_date 	no_membrs years_liv respondent_wall_… rooms 
<dbl> <chr> <dttm> <dbl> <dbl> <chr> <dbl> 
1 	3 God 2016-11-17 00:00:00 	10 	15 burntbricks 	
1 
# … with 7 more variables: memb_assoc <chr>, affect_conflicts <chr>, 
# liv_count <dbl>, items_owned <chr>, no_meals <dbl>, months_lack_food <chr>, 
# instanceID <chr> 

## equivalent to head_interviews <-head(interviews) 
head_interviews <-interviews[1:6, ]
```

 
`:` is a special function that creates numeric vectors of integers in increasing or decreasing order, test `1:10` and `10:1` for instance. You can also exclude certain indices of a data frame using the “`-`” sign: 

```
interviews[, -1] # The whole data frame, except the first column 
# A tibble: 131 x 13 
village interview_date no_membrs years_liv respondent_wall_type rooms <chr> <dttm> <dbl> <dbl> <chr> <dbl> 
1 God 2016-11-17 00:00:00 3 4 muddaub 1 
2 God 2016-11-17 00:00:00 7 9 muddaub 1 
3 God 2016-11-17 00:00:00 10 15 burntbricks 1 
4 God 2016-11-17 00:00:00 7 6 burntbricks 1 
5 God 2016-11-17 00:00:00 7 40 burntbricks 1 
6 God 2016-11-17 00:00:00 3 3 muddaub 1 
7 God 2016-11-17 00:00:00 6 38 muddaub 1 
8 Chirodzo 2016-11-16 00:00:00 12 70 burntbricks 3 
9 Chirodzo 2016-11-16 00:00:00 8 6 burntbricks 1 
10 Chirodzo 2016-12-16 00:00:00 12 23 burntbricks 5 
# … with 121 more rows, and 7 more variables: memb_assoc <chr>, 
# affect_conflicts <chr>, liv_count <dbl>, items_owned <chr>, no_meals<dbl>, 
# months_lack_food <chr>, instanceID <chr> interviews[-c(7:131), ] # Equivalent to head(interviews) 
# A tibble: 6 x 14 
key_ID village interview_date no_membrs years_liv respondent_wall_… rooms 
<dbl> <chr> <dttm> <dbl> <dbl> <chr> <dbl> 
1 1 God 2016-11-17 00:00:00 3 4 muddaub 1 
2 1 God 2016-11-17 00:00:00 7 9 muddaub 1 
3 3 God 2016-11-17 00:00:00 10 15 burntbricks 1 
4 4 God 2016-11-17 00:00:00 7 6 burntbricks 1 
5 5 God 2016-11-17 00:00:00 7 40 burntbricks 1 
6 6 God 2016-11-17 00:00:00 3 3 muddaub 1 

# … with 7 more variables: memb_assoc <chr>, affect_conflicts <chr>, 
# liv_count <dbl>, items_owned <chr>, no_meals <dbl>, months_lack_food <chr>, 
# instanceID <chr> 
```


Data frames can be subset by calling indices (as shown previously), but also by calling their column names directly: 

```
interviews["village"] # Result is a data frame 
interviews[, "village"] # Result is a data frame 
interviews[["village"]] # Result is a vector 
interviews$village # Result is a vector 
```

#### Exercise 
---

1. Create a data frame (`interviews_100`) containing only the data in row 100 of the `interviews` dataset. 

2. Notice how `nrow()` gave you the number of rows in a data frame? 
* Use that number to pull out just that last row in the data frame. 
* Compare that with what you see as the last row using `tail()` to make sure it’s meeting expectations. 
* Pull out that last row using `nrow()` instead of the row number. 
* Create a new data frame (`interviews_last`) from that last row. 

3. Using the number of rows in the interviews dataset that you found in question 2, extract the row that is in the middle of the dataset. Store the content of this middle row in an object named `interviews_middle`. (hint: This dataset has an odd number of rows, so finding the middle is a bit trickier than dividing `n_rows` by `2`. Use the `median()` function and what you’ve learned about sequences in R to extract the middle row!) 

4. Combine `nrow()` with the `-` notation above to reproduce the behavior of `head(interviews)`, keeping just the first through 6th rows of the interviews dataset. 


