---
layout: default
title: Version Control with Git
parent: GitHub and GitHub Pages
has_children: true
nav_order: 2
---

# Version Control with Git
Hosted by the [Carnegie Mellon University (CMU) Libraries](https://www.library.cmu.edu/)

## About this workshop

This workshop is for those beginning to explore the concept of version control, as well as anyone seeking to refine their skills.
Git is a version control system that lets you manage and track changes to files on your computer through the command line interface.
Topics covered will include configuring a local repository on your computer, modifying files and committing changes, and exploring version histories.

____
### Presenters
Sarah Young <a href='https://github.com/rootsandberries' target='_blank'><img src='../content/img/GitHub-Mark-custom.svg' style='width:15px; padding:0; border:none !important;'></a>  
Principal Librarian  
Office: 109G, Hunt Library  
[sarahy@andrew.cmu.edu](mailto:sarahy@andrew.cmu.edu)

Chasz Griego <a href='https://github.com/chaszg' target='_blank'><img src='../content/img/GitHub-Mark-custom.svg' style='width:15px; padding:0; border:none !important;'></a>  
Science and Engineering Librarian    
Office: 4416, Sorrells Library  
[cgriego@andrew.cmu.edu](mailto:cgriego@andrew.cmu.edu)

### Learning Objectives

Workshop attendees will be able to:

1. Understand the benefits of an automated version control system  
2. Configure settings in Git  
3. Create a local Git repository  
4. Track changes to files with commits  

### Setup

To be best prepared for this workshop, please follow the [setup instructions](./setup)
prior to attending.

### Interactive Notepad

During the workshop, you can ask and answer questions in this
[Etherpad](https://etherpad.wikimedia.org/p/2023-09-15-GIT), a notepad
for live collaboration.  

### Pre-Workshop Survey

Before the start of the workshop, please complete this
[survey](https://forms.gle/NHBUaBKbGq92N4wT8). Thank you!!

### Schedule

| Section  | Time
| ------------- | -------------
| [Setup](./setup.md) and Pre-Workshop Survey  |   
| [Automated Version Control](01-basics.md) | 00:00  
| [Setting Up Git](02-setup.md)  | 00:05  
| [Creating a Repository](03-create.md)  |  00:10  
| [Tracking Changes](04-changes.md) | 00:20
| Break | 00:25   
| [Exploring History](05-history.md) | 00:45   
| [Ignoring Things](06-ignore.md) | 01:10   
| Post-Workshop Survey | 01:20  
| Finish  | 01:30  

### Spooky Space Explorers

Wolfman and Dracula have been hired by Universal Missions (a space
services spinoff from Euphoric State University) to investigate if it
is possible to send their next planetary lander to Mars.  They want to
be able to work on the plans at the same time, but they have run into
problems doing this in the past.  If they take turns, each one will
spend a lot of time waiting for the other to finish, but if they work
on their own copies and email changes back and forth things will be
lost, overwritten, or duplicated.

A colleague suggests using [version control](learners/reference.md#version-control) to
manage their work. Version control is better than mailing files back and forth:

- Nothing that is committed to version control is ever lost, unless
  you work really, really hard at it. Since all old versions of
  files are saved, it's always possible to go back in time to see
  exactly who wrote what on a particular day, or what version of a
  program was used to generate a particular set of results.

- As we have this record of who made what changes when, we know who to ask
  if we have questions later on, and, if needed, revert to a previous
  version, much like the "undo" feature in an editor.

- When several people collaborate in the same project, it's possible to
  accidentally overlook or overwrite someone's changes. The version control
  system automatically notifies users whenever there's a conflict between one
  person's work and another's.

Teams are not the only ones to benefit from version control: lone
researchers can benefit immensely.  Keeping a record of what was
changed, when, and why is extremely useful for all researchers if they
ever need to come back to the project later on (e.g., a year later,
when memory has faded).

Version control is the lab notebook of the digital world: it's what
professionals use to keep track of what they've done and to
collaborate with other people.  Every large software development
project relies on it, and most programmers use it for their small jobs
as well.  And it isn't just for software: books,
papers, small data sets, and anything that changes over time or needs
to be shared can and should be stored in a version control system.

>## Prerequisites
>
>In this lesson we use Git from the Unix Shell.
>Some previous experience with the shell is expected,
>*but isn't mandatory*.

### Post-Workshop Survey

Please complete this [survey](https://forms.gle/aJVt7AjGEyqR9URu8)
after attending the workshop. Thank you!!!

### Acknowledgment

*The material for this workshop was created from the
[Version Control with Git](https://swcarpentry.github.io/git-novice/) curriculum
developed by [The Software Carpentry Foundation](https://software-carpentry.org/)
of [The Carpentries](https://carpentries.org/) licensed under
[CC-BY 4.0](https://swcarpentry.github.io/git-novice/LICENSE.html)*
