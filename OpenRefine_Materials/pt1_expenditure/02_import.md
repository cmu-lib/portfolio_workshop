---
layout: default
parent: Part 1: OpenRefine Basics with Personal Consumption Expeditures Data
has_children: false
nav_order: 2
title: Importing data
---

## Review the dataset and load it into OpenRefine1. Open the file expenditures\_by_state.xlsx in Excel and take a look at it. This is a freely available dataset from the Bureau of Economic Analysis, which provides average expenditures on a wide range of goods and services. Notice the following:

	* The data file has been formatted for reading rather than analysis. It has a blank column A. It has some rows at the top containing descriptive information that is not part of the data table. We can also see that each state is only listed once, which is fine for viewing, but will mess things up if we try to sort the data in order to analyze it.	* The “Expenditure” column has leading spaces in it.

2. Close the Excel file. Next, start up OpenRefine.3. Ensure that Create Project is selected. Click on Choose Files. Browse to the file expenditures\_by_state.xlsx. Click Open. Then, click the Next button.4. You are now viewing the dataset in Preview view. Here you can see what data will look like when loaded, and make some changes to the dataset. Notice the following:
	* The descriptive text at the top of the Excel worksheet is showing in the preview, and is messing up OpenRefine’s ability to identify the column headings. We can instruct OpenRefine to ignore these rows that aren’t part of the data table. **Select the check box beside Ignore first, and type 6 in the box to ignore the first 6 lines at the beginning of the file.**	* Numbers are displayed in green--this means OpenRefine has recognized these columns as containing numeric data 

5. In the Project name box, give the project a name of your choice. Click Create Project.6. Your data has now been loaded into OpenRefine. Note that it has stored a copy of this data with the OpenRefine installation files on your computer. When you make edits using OpenRefine, you are not editing the original data file you uploaded, all edits are made to the copy OpenRefine has created.
