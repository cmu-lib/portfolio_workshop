---
layout: default
grand_parent: Cleaning Untidy Data with OpenRefine
parent: Part 1 OpenRefine Basics with Personal Consumption Expeditures Data
has_children: false
nav_order: 5
title: Transposing data
---

## Transpose the data from wide format to long format

1. **Wide vs. Long format:** The dataset is currently in “wide” format with years across as columns. We should convert it to “long” format to work with it using numeric facets. Converting to long format will put all the years into one column as a 'Year' variable, and all the numeric data values into a second column. 
2. **Transpose the data to long format:** Remove an facets you have in place. From the 2017 column pull down menu, select Transpose -> Transpose cells across columns into rows....The Transpose window appears. You are going to put the data from the 8 numeric data columns (named 2010 through 2017) into two columns, one containing the year, and one containing the numeric data value (representing an expenditure amount). For the *From column*, choose 2010. For the *To column* choose 2017 (or last column, either will work). In the Transpose into section, we will use the Two new columns option. The Key Column will be the years – call it Year. Give the Value Column the name Per\_capita_expenditure. Check the Fill down in other columns option. Click Transpose.

![Transpose set up image](/fig/transpose_setup_image_openrefine.jpg)

**Note:** For each state, for each expenditure type, we now have 8 separate rows, one for each year. Notice the dataset now has 9792 rows, compared to 1224 before transposing. It has fewer columns, but many more rows – this is why it is referred to as a “long” format. Long format can be useful for certain types of data analyses, where all your data measuring the same thing (e.g., per capita expenditures) need to be in one column instead of spread over many.
