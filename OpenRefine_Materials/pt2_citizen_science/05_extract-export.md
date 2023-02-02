---
layout: default
grand_parent: Cleaning Untidy Data with OpenRefine
parent: Part 2 Advanced Data Cleaning with Citizen Science Data
has_children: false
nav_order: 5
title: Extracting JSON script and shutting down OpenRefine
---

## Extract a JSON script to reproduce your steps with another data file

1. If you have a similarly structured dataset – perhaps for a different snapshot in time – and want to perform the same steps, we can extract a JSON script for future use. Click on the Undo/Redo tab and click on Extract. Choose the steps you want to repeat. Copy the code and save it in a text file to keep a copy of your steps. Later if you load up your new dataset, you could go back to the Undo/Redo tab and select Apply and paste in this code into the window to run those steps on the new dataset.

### Activity 4 
Start up a new project and load the citizen science dataset again. Apply the JSON code that we just copied by going to the Undo/Redo tab, clicking Apply and copying and pasting the code into the window. Click Perform Operations.

## Shutting down OpenRefine

1. To ensure that all of your steps are saved, it is important to properly shut down OpenRefine.  
	* On a PC, hit Control-C on your keyboard.
	* On a Mac, go to the OpenRefine app in the doc and choose Quit.