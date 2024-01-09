---
layout: default
grand_parent: Introduction to R Getting started with R and RStudio
parent: Introduction to R Part 2
has_children: false
nav_order: 6
title: Exporting data
---

## Exporting data 
Now that you have learned how to use **dplyr** to extract information from or summarize your raw data, you may want to export these new data sets to share them with your collaborators or for archival. 

Similar to the `read_csv()` function used for reading CSV files into R, there is a `write_csv()` function that generates CSV files from data frames. 

Before using `write_csv()`, we are going to create a new folder, `data_output`, in our working directory that will store this generated dataset. We don’t want to write generated datasets in the same directory as our raw data. It’s good practice to keep them separate. The `data` folder should only contain the raw, unaltered data, and should be left alone to make sure we don’t delete or modify it. In contrast, our script will generate the contents of the `data_output` directory, so even if the files it contains are deleted, we can always re-generate them.   

Imagine you wanted to use the reduced size dataset from the piping exercise above in a new project. If you remember, we used the following code to filter only those records where the village name was “Chirodzo” and select only the variables `village` through `respondent_wall_type`, and stored the results in a new object called `interviews_ch`. 

```
interviews_ch <- interviews %>% 
	filter(village == "Chirodzo") %>% 
	select(village:respondent_wall_type) 
interviews_ch 
# A tibble: 39 x 5 
village interview_date no_membrs years_liv respondent_wall_type 
<chr> <dttm> <dbl> <dbl> <chr> 
1 Chirodzo 2016-11-16 00:00:00 12 70 burntbricks 
2 Chirodzo 2016-11-16 00:00:00 8 6 burntbricks 
3 Chirodzo 2016-12-16 00:00:00 12 23 burntbricks 
4 Chirodzo 2016-11-17 00:00:00 8 18 burntbricks 
5 Chirodzo 2016-11-17 00:00:00 5 45 muddaub 
6 Chirodzo 2016-11-17 00:00:00 6 23 sunbricks 
7  Chirodzo  2016-11-17  00:00:00  3  8  burntbricks  
8  Chirodzo  2016-11-17  00:00:00  7  29  muddaub  
9  Chirodzo  2016-11-17  00:00:00  2  6  muddaub  
10  Chirodzo  2016-11-17  00:00:00  9  7  muddaub  
#  …  with  29  more  rows 
``` 

Now we can save this data frame to our `data_output` directory. 

```
write_csv(interviews_ch, file = "data_output/interviews_ch.csv") 
```

#### Key Points 
---
* Use the dplyr package to manipulate data frames. 
* Use select() to choose variables from a data frame. 
* Use filter() to choose data based on values. 
* Use group_by() and summarize() to work with subsets of data. 
* Use mutate() to create new variables. 




