---
layout: default
parent: Part 1: OpenRefine Basics with Personal Consumption Expeditures Data
has_children: true
nav_order: 3
title: Basic data cleanup
---

## Perform some basic data cleanup 1. In the top toolbar, select 50 in order to show more rows on the screen at once.
2. **Remove the blank columns:**. Look for the pull down menu for the column named “Column”. From the pull down menu, selectEdit Column -> Remove this Column.
3. **Change a column name:** Click on the pull down menu for the column name "GeoName". Under Edit Column, choose Rename this Column. Rename the column to "State" and click OK.
3. **Fill down data:** We want to fill the entries down in the State column so that all rows have a state associated with them. From the State column pull down menu, select Edit Cells -> Fill Down. In the top toolbar, click next a few times in order to look at a few pages of results. Verify that the fill operation seems to have worked.4. **Delete leading whitespace:** Hover your cursor over a cell in the Expenditure column and click edit. You’ll see that there are leading whitespaces that could cause problems down the road. Click 'Cancel' to close the Edit window. From the Expenditure column pull down menu, select Edit cells -> Common transforms -> Trim leading and trailing white space. Check a cell to verify that the leading spaces are gone.

