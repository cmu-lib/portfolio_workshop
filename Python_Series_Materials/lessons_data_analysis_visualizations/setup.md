---
layout: default
grand_parent: Python for Data Science
parent: Series - Data Analysis and Visualization with Python
has_children: false
nav_order: 1
title: Setup
---
# Setup
## Data

Data for this lesson is from the
[Portal Project Teaching Database](https://figshare.com/articles/Portal_Project_Teaching_Database/1314459).
Please [download all the files as a zip](https://datacarpentry.github.io/python-ecology-lesson/data/portal-teachingdb-master.zip) which will give you everything in a single compressed file. You'll need to unzip
this file after downloading it.

## Installing Python using Anaconda

[Python][python] is a popular language for scientific computing, and great for
general-purpose programming as well. Installing all of the scientific 
packages we use in the lesson individually can be a bit cumbersome, 
and therefore recommend the all-in-one installer [Anaconda][anaconda].

Regardless of how you choose to install it, please make sure you 
install Python version 3.x (e.g., 3.10 is fine and will continue to receive 
security patches unitl 2026-OCT-04).

## Installing Anaconda

### Windows

1. Open [https://www.anaconda.com/products/individual](https://www.anaconda.com/products/individual) in your 
   web browser.

2. Download the Anaconda Python 3 installer for Windows.

3. Double-click the executable and install Python 3 using the 
   recommended settings. Make sure that **Register Anaconda as 
   my default Python 3.x** option is checked -- it should be in the 
   latest version of Anaconda.

4. Verify the installation: click Start, search and select 
   `Anaconda Prompt` from the menu. A window should pop up 
   where you can now type commands such as checking your 
   Conda installation with:
  
  ```bash
  conda --help
  ```

### MacOS

1. Visit [https://www.anaconda.com/products/individual](https://www.anaconda.com/products/individual) in your 
   web browser.

2. Download the Anaconda Python 3 installer for macOS. These 
   instructions assume that you use the graphical installer `.pkg` file.

3. Follow the Anaconda Python 3 installation instructions. Make 
   sure that the install location is set to "Install only for me" so 
   Anaconda will install its files locally, relative to your home 
   directory. Installing the software for all users tends to create 
   problems in the long run and should be avoided.

4. Verify the installation: click the Launchpad icon in the Dock, type 
   Terminal in the search field, then click Terminal. A window should 
   pop up where you can now type commands such as checking 
   your conda installation with:
  
  ```bash
  conda --help
  ```

### Linux

Note that the following installation steps require you to work from the terminal (shell).
If you run into any difficulties, please request help before the workshop begins.

1. Open [https://www.anaconda.com/products/individual](https://www.anaconda.com/products/individual) in your web browser.

2. Download the Anaconda Python 3 installer for Linux.

3. Install Anaconda using all of the defaults for installation.
  
  - Open a terminal window.
  - Navigate to the folder where you downloaded the installer.
  - Type `bash Anaconda3-` and press <kbd>Tab</kbd>.
    The name of the file you just downloaded should appear.
  - Press <kbd>Return</kbd>
  - Follow the text-only prompts.  When the license agreement appears (a colon
    will be present at the bottom of the screen) press <kbd>Spacebar</kbd> until you see the
    bottom of the text. Type `yes` and press <kbd>Return</kbd> to approve the license. Press
    <kbd>Return</kbd> again to approve the default location for the files. Type `yes` and
    press <kbd>Return</kbd> to prepend Anaconda to your `PATH` (this makes the Anaconda
    distribution your user's default Python).

4. Verify the installation:
  this depends a bit on your Linux distribution, but often you will have an Applications listing
  in which you can select a Terminal icon you can click. A window should pop up where you can now
  type commands such as checking your conda installation with:
  
  ```bash
  conda --help
  ```

## Required Python Packages

The following are packages needed for this workshop:

- [Pandas](https://pandas.pydata.org/)
- [Jupyter notebook][jupyter]
- [Numpy](https://numpy.org/)
- [Matplotlib](https://matplotlib.org/)

All packages will have automatically been installed with Anaconda.

## Required packages: Miniconda

Miniconda is a lightweight version of Anaconda. If you install Miniconda instead of Anaconda,
you need to install required packages manually in the following way:

```bash
conda install -y numpy pandas matplotlib jupyter
```

## Launch a Jupyter notebook

After installing either Anaconda or Miniconda and the workshop packages,
launch a Jupyter notebook by typing this command into the *terminal* or *anaconda-prompt*:

```bash
jupyter notebook
```

The notebook should open automatically in your browser. If it does not or you
wish to use a different browser, open this link: [http://localhost:8888](https://localhost:8888).
### Leaving the terminal used to launch Jupyter open

Jupyter depends on a server running in the background associated with the window used to launch it. Closing that window will results in web interface errors in the web interface. When done, you can either close the terminal or shut down the server using <kbd>CTRL</kbd>+<kbd>C</kbd> and submitting <kbd>y</kbd> within 5 seconds if the terminal is needed for other tasks.

### How the Jupyter notebook works

After typing the command `jupyter notebook`, the following happens:

- A Jupyter Notebook server is automatically created on your local machine.

- The Jupyter Notebook server runs locally on your machine only and does not
  use an internet connection.

- The Jupyter Notebook server opens the Jupyter notebook client, also known
  as the notebook user interface, in your default web browser.
  
  ![Jupyter notebook file browser](../fig/00_1_jupyter_file_browser.png)
  *The Jupyter notebook file browser*

- To create a new Python notebook select "Python 3" from the "New" dropdown on the upper
  right of the screen.
  
  ![Jupyter notebook file browser](../fig/00_2_jupyter_new_notebook.png)
  *The Jupyter notebook file browser*

- When you can create a new notebook and type code into the browser, the web
  browser and the Jupyter notebook server communicate with each other.
  
  ![new Jupyter notebook](../fig/00_3_jupyter_blank_notebook.png)
  *A new, blank Jupyter notebook*

- Under the "help" menu, take a quick interactive tour of how to
  use the notebook. Help on Jupyter and key workshop packages is
  available here too.
  
  ![Jupyter tour and help](../fig/00_4_jupyter_tour_help.png)
  *User interface tour and Help*

- The Jupyter Notebook server does the work and calculations, and the web
  browser renders the notebook.

- The web browser then displays the updated notebook to you.

- For example, click in the first cell and type some Python code.
  
  ![Code cell](../fig/00_5_jupyter_code_before.png)
  *A Code cell*

- This is a **Code** cell (see the cell type dropdown with the word **Code**).
  To run the cell, type <kbd>Shift</kbd>\+<kbd>Return</kbd>.
  
  ![Code cell and its output](../fig/00_6_jupyter_code_after.png)
  *A Code cell and its output*

- Let's look at a **Markdown** cell. Markdown is a text manipulation
  language that is readable yet offers additional formatting. Don't forget
  to select **Markdown** from the cell type dropdown. Click in the cell and
  enter the markdown text.
  
  ![markdown input cell](../fig/00_7_jupyter_markdown_before.png)
  *A markdown input cell*

- To run the cell, type <kbd>Shift</kbd>\+<kbd>Return</kbd>.
  
  ![rendered markdown cell](../fig/00_8_jupyter_markdown_after.png)
  *A rendered markdown cell*

This workflow has several advantages:

- You can easily type, edit, and copy and paste blocks of code.
- Tab completion allows you to easily access the names of things you are using
  and learn more about them.
- It allows you to annotate your code with links, different sized text,
  bullets, etc. to make information more accessible to you and your
  collaborators.
- It allows you to display figures next to the code that produces them
  to tell a complete story of the analysis.

### How the notebook is stored

- The notebook file is stored in a format called JSON and has the suffix
  `.ipynb`.
- Just like HTML for a webpage, what's saved in a notebook file looks
  different from what you see in your browser.
- But this format allows Jupyter to mix software (in several languages) with
  documentation and graphics, all in one file.

### Notebook modes: Command and Edit

The notebook has two modes of operation: Command and Edit. Command mode lets
you edit notebook level features; while, Edit mode lets you change the
contents of a notebook cell. Remember a notebook is made up of a number of
cells which can contain code, markdown, html, visualizations, and more.

### Help and more information

Use the **Help** menu and its options when needed.

[python]: https://www.python.org/
[anaconda]: https://www.anaconda.com/
[jupyter]: https://jupyter.org/

## Acknowledgment

The material for this workshop series was created from the [Data Analysis and Visualization in Python for Ecologists](https://datacarpentry.github.io/python-ecology-lesson/) curriculum developed by [The Data Carpentry Foundation](https://datacarpentry.org/) of [The Carpentries](https://carpentries.org/) licensed under [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/)