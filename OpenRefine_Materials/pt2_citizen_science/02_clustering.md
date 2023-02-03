---
layout: default
grand_parent: Cleaning Untidy Data with OpenRefine
parent: Part 2 Advanced Data Cleaning with Citizen Science Data
has_children: false
nav_order: 2
title: Clustering
---

## Create a new project from the citizen science dataset 

1.  **Start a new project:** Start up OpenRefine (if it isn’t running) or click on the OpenRefine logo on the top left to go to the main screen. Note: If you were working with another project, it has been automatically saved in OpenRefine and the files are stored locally on your computer. You can see your project listed here and can use Open Projects to go back to it later. 
2. **Import your dataset:** Click on Create Project and import the citizenscience.csv file. Maintain the default settings, rename your project and click Create Project. You should see that there are 1991 records in our dataset. Click on show 50 rows to show more rows displayed in the window.

## Use the clustering feature to make your data consistent 

1. **Create a text facet:** Go to the species\_guess column (where our citizen scientists have made a guess as to what species they have observed). From the species_guess column pull down menu, select Facet->Text facet. 
2. **Examine your data:** You'll see that some of them are a bit unusual, and in those cases, you may want to edit them; however, in other cases, you'll see that there are two facets that look very similar, but just have different capitalization, such as American Pokeweed. When we have facets that look similar, we can use OpenRefine's clustering features to help improve the consistency of the values in that column. Click on the Cluster button at the top of the facet window.
3. **Set your clustering algorithm:** At the top of the screen, you'll see that there are different methods and keying functions you can choose from to find clusters. They roughly go from more strict/unforgiving to looser. Let's keep the default for now. Note: In this case, you should see that the column values are just variations in capitalization, but clustering can also catch typos, plural vs singular and other small differences as well.
4. **Cluster similar values:** You can see that it has found entries that it thinks are all referring to the same thing and suggests merging them under one recommended facet. You can put a check mark next to the ones you agree with, and edit the heading that you want to merge them into--or just click on the name you want to use. Go through and merge the entries found into new terms that have only the first word capitalized by adding a check mark under Merge? and adjusting the New Cell Value. When done, click on Merge Selected & Re-Cluster. You might've noticed that as you did a merge, it flashed at the top of the screen how many rows were affected/mass edited.

### Activity 2 
Try a different clustering algorithm and see if you can clean up the species\_guess column more. Try different clustering algorithms and see if you can clean up the species_guess column more. You can ‘Select All’ and quickly scan the suggestions to merge in bulk. After cleaning up the column, can you identify what the most common bird species is in the dataset?

### Bonus activity 
Find all of the blank cells in the common_name column and rename them to N/A. 
### Bonus activity 
In the coordinates_obscured column, change all 'false' values to '0' and all 'true' values to '1'.  