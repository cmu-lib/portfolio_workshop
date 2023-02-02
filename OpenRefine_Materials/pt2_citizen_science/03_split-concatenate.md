---
layout: default
parent: Part 2: Advanced Data Cleaning with Citizen Science Data
has_children: false
nav_order: 3
title: Splitting and concatenating
---

## Split columns in the dataset
1. **Split the scienctific name colunm into two:** We have a column called scientific\_name. With scientific names, the first part is the genus name and the second part is the specific name. So let's split this column so we can see how many of a particular genus were identified. From the scientific\_name column pull down menu, select Edit column-->Split into several columns. For the separator, put a space, split into 2 columns at most, and uncheck Remove this column because we want to keep it. Then click on OK.
2. **Edit column names:** From each new column’s pull down menu, select Edit column-->Rename this column. For the first one, call it genus. For the second one, call it specific. You could use text facets on the genus column to see how many of each genus were identified. From the genus column pull down menu, select Facet-->Text facet In the facet window, click on Sort by count to sort the facets and see which genus comes out on top.

## Concatenate columns in the dataset
1. **Add a new column based on an existing column:** You can concatenate (join) strings and/or values from two or more columns together. Let's say that we wanted to combine the information on the user id and login into one column with the format username (user id). For this example, we're going to create a new column to store this information using the *Add column based on this column* feature. From the user_id column pull down menu, select Edit column-->Add column based on this column. Give the new column the name User.

2. **Use GREL to define a format:** OpenRefine's scripting language is called GREL (Google Refine Expression Language). We can use it to define combinations of characters, strings, and numbers. In our expression to define a new column, value refers to the value of the current column. If we want to refer to another column in our expression we use the term **cells.** and then the name of a column then **.value** So for the expression in this case, type **cells.user_login.value + " (" + value + ")"**
The plus sign is used to join the different values or strings together into one long string. So we're creating a string that is the user login, a space, and then the user id in parentheses.

	* You'll notice that when you type in the expression, the preview at the bottom changes to show you what the resulting value will be. This preview is extremely helpful when writing GREL expressions! For more help with regular expressions, see [http://www.rexegg.com/regex-quickstart.html](http://www.rexegg.com/regex-quickstart.html) and [https://regex101.com/](https://regex101.com/).

### Actvity 3 
Concatenate the scientific\_name column with the common\_name in parentheses into a new column called Descriptive Name. The format should be \<scientific\_name> (\<common_name>). 

