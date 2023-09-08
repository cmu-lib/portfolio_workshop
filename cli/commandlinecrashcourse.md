### Table of Contents:

- Opening the command line 
- Navigating through files
- Creating files and directories
- Nano Text Editor
- Accessing command history
- Examine Content
- Copying and moving files
- Removing files and directories

#### Opening Command Line/Terminal
- Windows: 
    1. Click the Windows icon to bring up your start menu. Type cmd into the search box.
    2. Select the command prompt entry and click open.
    3. Occasionally, you must select the run as administrator option to use higher-level system commands.
 - Mac: 
    1. click command and space bar then type terminal
    2. click spotlight search icon (magnifying glass), then type terminal 

#### Navigating Through Files 

- `pwd` AKA print working directory
- `ls` AKA print a list of items in your working directory (including different options); 
   1. `ls -a` (show all) 
   2. `ls -F`(add trailing /) / means it's a directory and * means it's a program
   3. `ls -l`
   4. `ls -Fa`
   5. `ls -laF`
- Navigating up files
   1. `cd`
- Navigating down files
   2. `cd..` (move back a directory)
        - To view files in higher level directories can also do `ls ../` which will go back 2 levels and show your root/home directory (lbeltran) or go back 1 level `ls ../../` to see files in your Desktop directory  
  3. `cd ~` takes you straight to your root/home directory 
      - Question! What is the different between `cd..` and `cd~` ? 
- Relative and absolute paths
    1. A relative path always starts with / and gives the full address from the home directory (think of this as getting GPS coordinates, no matter where you are it will tell you where something is and how to get there) 
    2. An abosolute path will only give the address from the working directory, and does not start with a / (analogous to getting directions from someone on the street in real time)


#### Creating Files & Directories
- Navigate to their desktop & create 3 new directories. The first directory will be on your desktop. 
    - `mkdir name1`
- Navigate into doing `cd name1` and then make 2 directories. We can do this quickly by listing both names as shown below. Note, be careful you dont add a space in a name because that will make two directories!!
    - `mkdir name2 name3`
- Navitgate into `name2` directory 
    1. and create a nano text file

#### Nano Editor
- Open up the nano text editor or your favorite text editor. Note, this may be different for 
    - `nano` 
- Copy and paste [text](http://shakespeare.mit.edu/hamlet/full.html) 
    1. access help in nano by
        - (control G)
- Save the text (control C) and name the file `practicetext_1`
- Exit the editor (control X)



#### Accessing Command History

- To repeat the most recent/recently command run, use the up arrow
- The down arrow will take you forward in your in the command history  
    - Ctrl+C will cancel the command you are writing, and give you a fresh prompt.
    - Ctrl+R will do a reverse-search through your command history. This is very useful.
    - Ctrl+L or the clear command will clear your screen.


- To review recent command history
    - `history` 
- To rerun a specific command in your command history 
    - add a ! in front of the number
        - e.g., `!22`

#### Examining Files 

- To examine content in a file you can use `less`
    - `less practicetext1`
        - Space	to go forward
        - b	to go backward
        - g	to go to the beginning
        - G	to go to the end
        - q	to quit
    - `head practicetext_1`
    - `tail practicetext_1`
        1. use `-n` option after head/tail to print only the first or last line
    - `wc practicetext_1`
        1. to view the number of lines, words and characters in the file
    - `wc -l practicetext_1`
        2. to view only the number of lines
            
    
    
#### Copying and moving 
- Make a copy of the text file
    - `cp practicetext_1  practicetext_1_copy`
    - check that a copy of our text data was made `ls -F`
- Make a backup directory to store the copy of the text data and any copies
    - `mkdir backup`
    - Note: make sure you are creating directories in the correct working directory (i.e., make sure you are in the right working directory)
- Move your copy of the text data into the backup directory
    - `mv practicetext_1_copy backup`
- You can either navigate to backup and type ls OR type `ls backup`
- Rename the copy of the text
    - `mv` also let's you rename files 
        - `mv practicetext_1_copy practicetext_1_backup`

#### Removing Files & Directories

- Remove the backup copy of the text file
    - `rm practicetext_1_backup`
- Remove all of the directories under name1
    - `rm -r name1`
        - A recursive flag `-r` will need to be added to tell rm to remove a directory
    - Note, remove will permanently delete a file but also any content in a directory (i.e., not only the directory name1 but will also remove everything in the directory)
    
##### That's all folks!
    


```python

```
