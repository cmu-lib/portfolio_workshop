---
layout: default
parent: Introduction to Command Line Interface
has_children: false
nav_order: 2
title: Setup
---

# Setup

### Getting the Data
The data we will use is taken from the [Software Carpentries](https://software-carpentry.org). To obtain it, download the file [here](https://swcarpentry.github.io/shell-novice/data/shell-lesson-data.zip) and unzip it. Please save the data to a folder called `data` on your desktop

### Install Shell Software
If you do not already have the shell software installed, you will need to download and install it. (See below)

### Opening Shell
After installing the software

Open a terminal. If you’re not sure how to open a terminal on your operating system, see the instructions below. In the terminal type cd then press the Enter or Return key. This step will make sure you start with your home folder as your working directory. In the lesson, you will find out how to access the data files in this folder.

### Installing Bash
If you have a Mac or Linux operating system then you should have access to Bash through your terminal or command prompt.

If you use

Microsoft
Mac
Linux

### Microsoft
1. Download the Git for Windows [installer] (https://gitforwindows.org/).
2. Run the installer and follow the steps below:
Click on "Next" four times (two times if you've previously installed Git). You don't need to change anything in the Information, location, components, and start menu screens.

From the dropdown menu, *"Choosing the default editor used by Git", select "Use the Nano editor by default" (NOTE: you will need to scroll up to find it) and click on "Next".*

On the page that says "Adjusting the name of the initial branch in new repositories", ensure that "Let Git decide" is selected. This will ensure the highest level of compatibility for our lessons.

Ensure that "Git from the command line and also from 3rd-party software" is selected and click on "Next". (If you don't do this Git Bash will not work properly, requiring you to remove the Git Bash installation, re-run the installer and to select the "Git from the command line and also from 3rd-party software" option.)

Select "Use bundled OpenSSH".

Ensure that "Use the native Windows Secure Channel Library" is selected and click on "Next".

Ensure that "Checkout Windows-style, commit Unix-style line endings" is selected and click on "Next".

Ensure that "Use Windows' default console window" is selected and click on "Next".

Ensure that "Default (fast-forward or merge) is selected and click "Next"

Ensure that "Git Credential Manager" is selected and click on "Next".

Ensure that "Enable file system caching" is selected and click on "Next".

Click on "Install".

Click on "Finish" or "Next".

3. If your "HOME" environment variable is not set (or you don't know what this is):
Open command prompt (Open Start Menu then type cmd and press Enter)

Type the following line into the command prompt window exactly as shown:
setx HOME "%USERPROFILE%"

Press Enter, you should see SUCCESS: Specified value was saved.

Quit command prompt by typing exit then pressing Enter

This will provide you with both Git and Bash in the Git Bash program.

### Video Tutorial

Video Tutorial
<iframe width="560" height="315" src="https://www.youtube.com/embed/339AEqk9c-8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>  
