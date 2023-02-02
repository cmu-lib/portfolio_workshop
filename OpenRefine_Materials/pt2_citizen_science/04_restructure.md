---
layout: default
grand_parent: Cleaning Untidy Data with OpenRefine
parent: Part 2: Advanced Data Cleaning with Citizen Science Data
has_children: false
nav_order: 4
title: Restructuring data
---

## Restructure the dataset by removing columns and rows, and then work with Undo/Redo to roll those changes back
1. **Delete columns in bulk:** Go to the special All column pull down menu on the far left. From the All column pull down menu, select Edit columns->Re-order / remove columns... From here you can drag columns from the left to the right to remove them – do this for private latitude and private longitude. We can also reorder columns. Move license, species\_guess and quality_grade columns to just under id to move those columns more to the left. Click on OK to make the changes.
2. **Flag or star rows:** Click on the flag symbol next to a row of interest – try flagging the first few rows of the dataset. 
3. **Use facets to define and flag a subset:** From the license column pull down menu, select Facet-->Customized facets-->Facet by blanks. Click on true to show only the rows where that column is blank (i.e., rows where no license has been specified). From the quality_grade column pull down menu, select Facet-->Text facet Select the casual facet. Now we have a subset of rows that have a blank for license and are casual observations. Let's say that these 18 rows were no good to use. We could flag them (or star them or remove them). From the All column pull down menu, select Edit rows->Flag rows
4. **Remove flagged rows:** Reset all facets by clicking on the Reset All button on the left above the facet windows. Now you should see all the rows in your dataset again, some are flagged and some are not. Later if you decide that you want to remove those flagged rows that you were unsure of, you can. From the All column pull down menu, select Facet-->Facet by flag and then select true from the facet window to show only your flagged rows. You can delete all of them. From the All column pull down menu, select Edit rows-->Remove all matching rows. All the flagged rows should now be removed from the dataset. Reset all facets again by clicking on the Reset All button on the left above the facet windows to see your remaining rows.
5. **Undo and redo actions:** Click on the Undo/Redo tab above where the facets show up. You'll see a number of steps that outlines everything we did to this dataset. It is a great way to keep track of what you've done. You can also roll back your changes to a previous version by clicking on the last step you were happy with. Then everything after that has been rolled back. You can go back and forth in time to take a look at the dataset at a particular point. For example, click on the item that says Reorder columns. You'll see that the steps after that have greyed out, which means they haven't happened yet. So for this example, those flagged rows have now not be deleted, and you should see them in your dataset.
 
* Note: If you go back to a previous step (like we’ve just done), and then start making new changes/transformations - all the subsequent steps will be deleted permanently.

> **Bonus: Removing Duplicates**
> A common clean up process is the removal of items that are duplicates based on one or more columns. For a step-by-step guide to using faceting for this purpose, see [https://guides.library.illinois.edu/openrefine/duplicates](https://guides.library.illinois.edu/openrefine/duplicates). 