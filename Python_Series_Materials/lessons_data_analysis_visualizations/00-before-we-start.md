---
layout: default
grand_parent: Python for Data Science
parent: Series - Data Analysis and Visualization with Python
has_children: false
nav_order: 2
title: Before We Start
---
# Before we start

## Objectives

- Present motivations for using Python.
- Organize files and directories for a set of analyses as a Python project, and understand the purpose of the working directory.
- How to work with Jupyter Notebook.
- Know where to find help.
- Demonstrate how to provide sufficient information for troubleshooting with the Python user community.

## Questions

- What is Python and why should I learn it?

## What is Python?

Python is a general purpose programming language that supports rapid development of data analytics
applications.  The word "Python" is used to refer to both, the programming language and the tool
that executes the scripts written in Python language.

Its main advantages are:

- Free
- Open-source
- Available on all major platforms (macOS, Linux, Windows)
- Supported by Python Software Foundation
- Supports multiple programming paradigms
- Has large community
- Rich ecosystem of third-party packages

*So, why do you need Python for data analysis?*

- **Easy to learn:**
  Python is easier to learn than other programming languages. This is important because lower barriers
  mean it is easier for new members of the community to get up to speed.

- **Reproducibility:**
  Reproducibility is the ability to obtain the same results using the same dataset(s) and analysis.
  
  Data analysis written as a Python script can be reproduced on any platform.  Moreover, if you
  collect more or correct existing data, you can quickly re-run your analysis!
  
  An increasing number of journals and funding agencies expect analyses to be reproducible,
  so knowing Python will give you an edge with these requirements.

- **Versatility:**
  Python is a versatile language that integrates with many existing applications to enable something
  completely amazing.  For example, one can use Python to generate manuscripts, so that if you need to
  update your data, analysis procedure, or change something else, you can quickly regenerate all the
  figures and your manuscript will be updated automatically.
  
  Python can read text files, connect to databases, and many other data formats, on your computer or
  on the web.

- **Interdisciplinary and extensible:**
  Python provides a framework that allows anyone to combine approaches from different research
  (but not only) disciplines to best suit your analysis needs.

- **Python has a large and welcoming community:**
  Thousands of people use Python daily. Many of them are willing to help you through mailing lists and
  websites, such as [Stack Overflow][stack-overflow]  and [Anaconda community portal][anaconda-community].

## Knowing your way around Anaconda

[Anaconda][anaconda] distribution of Python includes a lot of its popular packages,
such as the IPython console, Jupyter Notebook, and Spyder IDE.
Have a quick look around the Anaconda Navigator. You can launch programs from the Navigator or use the command line.

The [Jupyter Notebook](https://jupyter.org) is an open-source web application that allows you to create
and share documents that allow one to create documents that combine code, graphs, and narrative text.
[Spyder][spyder-ide] is an **Integrated Development Environment** that
allows one to write Python scripts and interact with the Python software from within a single interface.

Anaconda comes with a package manager called [conda](https://conda.io/docs/)
used to install and update additional packages.


## Research Project: Best Practices

It is a good idea to keep a set of related data, analyses, and text in a single folder.
All scripts and text files within this folder can then use relative paths to the data files.
Working this way makes it a lot easier to move around your project and share it with others.

### Organizing your working directory

Using a consistent folder structure across your projects will help you keep things organized,
and will also make it easy to find/file things in the future. This can be especially helpful
when you have multiple projects. In general, you may wish to create separate directories for
your scripts, data, and documents.

- **`data/`**: Use this folder to store your raw data. For the sake of transparency and provenance,
  you should always keep a copy of your **raw data**. If you need to cleanup data, do it
  programmatically (*i.e.* with scripts) and make sure to separate cleaned up data from the raw data.
  For example, you can store raw data in files `./data/raw/` and clean data in `./data/clean/`.

- **`documents/`**: Use this folder to store outlines, drafts, and other text.

- **`code/`**: Use this folder to store your (Python) scripts for data cleaning, analysis, and
  plotting that you use in this particular project.

You may need to create additional directories depending on your project needs, but these should form
the backbone of your project's directory. For this workshop, we will need a `data/` folder to store
our raw data, and we will later create a `data_output/` folder when we learn how to export data as
CSV files.

## How to learn more after the workshop?

The material we cover during this workshop will give you an initial taste of how you can use Python
to analyze data for your own research. However, you will need to learn more to do advanced
operations such as cleaning your dataset, using statistical methods, or creating beautiful graphics.
The best way to become proficient and efficient at Python, as with any other tool, is to use it to
address your actual research questions. As a beginner, it can feel daunting to have to write a
script from scratch, and given that many people make their code available online, modifying existing
code to suit your purpose might make it easier for you to get started.

## Seeking help

* check under the *Help* menu
* type `help()`
* type `?object` or `help(object)` to get information about an object
* [Python documentation][python-docs]
* [Pandas documentation][pandas-docs]
* Search the internet: 
  paste the last line of your error message or the word "python" and a short description of what you want to do into your favourite search engine 
  and you will usually find several examples where other people have encountered the same problem and came looking for help.
    * [StackOverflow](https://stackoverflow.com/questions) can be particularly helpful for this: answers to questions are presented as a ranked thread ordered according to how useful other users found them to be. 
    Search using the `[python]` tag. 
    Most questions have already been answered, but the challenge is to use the right words in the search to find the answers: [https://stackoverflow.com/questions/tagged/python?tab=Votes][so-python]
    * **Take care:** copying and pasting code written by somebody else is risky unless you understand exactly what it is doing!
* ask somebody "in the real world". 
  If you have a colleague or friend with more expertise in Python than you have, show them the problem you are having and [ask them for help](#asking-for-help).
  During this workshop, don't hesitate to talk to your neighbour, compare your answers, and ask for help. 
  You might also be interested in organizing regular meetings following the workshop to keep learning from each other.
* Sometimes, the act of articulating your question can help you to identify what is going wrong.
  This is known as ["rubber duck debugging"](https://en.wikipedia.org/wiki/Rubber_duck_debugging) among programmers.

### Asking for help

The key to receiving help from someone is for them to rapidly grasp your problem. You should make it
as easy as possible to pinpoint where the issue might be.

Try to use the correct words to describe your problem. For instance, a package is not the same thing
as a library. Most people will understand what you meant, but others have really strong feelings
about the difference in meaning. The key point is that it can make things confusing for people
trying to help you. Be as precise as possible when describing your problem.

If possible, try to reduce what doesn't work to a simple reproducible example. If you can reproduce
the problem using a very small data frame instead of your 50,000 rows and 10,000 columns one,
provide the small one with the description of your problem. When appropriate, try to generalize what
you are doing so even people who are not in your field can understand the question. For instance,
instead of using a subset of your real dataset, create a small (3 columns, 5 rows) generic one.

### Generative AI

It is increasingly common for people to use _generative AI_ chatbots such as ChatGPT to get help while coding. 
You will probably receive some useful guidance by presenting your error message to the chatbot and asking it what went wrong. 
However, the way this help is provided by the chatbot is different. 
Answers on StackOverflow have (probably) been given by a human as a direct response to the question asked. 
But generative AI chatbots, which are based on an advanced statistical model, respond by generating the _most likely_ sequence of text that would follow the prompt they are given.

While responses from generative AI tools can often be helpful, they are not always reliable. 
These tools sometimes generate plausible but incorrect or misleading information, so (just as with an answer found on the internet) it is essential to verify their accuracy.
You need the knowledge and skills to be able to understand these responses, to judge whether or not they are accurate, and to fix any errors in the code it offers you.

In addition to asking for help, programmers can use generative AI tools to generate code from scratch; extend, improve and reorganise existing code; translate code between programming languages; figure out what terms to use in a search of the internet; and more.
However, there are drawbacks that you should be aware of.

The models used by these tools have been "trained" on very large volumes of data, much of it taken from the internet, and the responses they produce reflect that training data, and may recapitulate its inaccuracies or biases.
The environmental costs (energy and water use) of LLMs are a lot higher than other technologies, both during development (known as training) and when an individual user uses one (also called inference). For more information see the [AI Environmental Impact Primer](https://huggingface.co/blog/sasha/ai-environment-primer) developed by researchers at HuggingFace, an AI hosting platform. 
Concerns also exist about the way the data for this training was obtained, with questions raised about whether the people developing the LLMs had permission to use it.
Other ethical concerns have also been raised, such as reports that workers were exploited during the training process.

**We recommend that you avoid getting help from generative AI during the workshop** for several reasons:

1. For most problems you will encounter at this stage, help and answers can be found among the first results returned by searching the internet.
2. The foundational knowledge and skills you will learn in this lesson by writing and fixing your own programs are essential to be able to evaluate the correctness and safety of any code you receive from online help or a generative AI chatbot. 
   If you choose to use these tools in the future, the expertise you gain from learning and practising these fundamentals on your own will help you use them more effectively.
3. As you start out with programming, the mistakes you make will be the kinds that have also been made -- and overcome! -- by everybody else who learned to program before you. 
  Since these mistakes and the questions you are likely to have at this stage are common, they are also better represented than other, more specialised problems and tasks in the data that was used to train generative AI tools.
  This means that a generative AI chatbot is _more likely to produce accurate responses_ to questions that novices ask, which could give you a false impression of how reliable they will be when you are ready to do things that are more advanced.

## More resources

- [PyPI - the Python Package Index][pypi]

- [The Hitchhiker's Guide to Python][python-guide]

- [Dive into Python 3][dive-into-python3]



[stack-overflow]: https://stackoverflow.com
[anaconda-community]: https://www.anaconda.com/community
[anaconda]: https://www.anaconda.com/download
[spyder-ide]: https://www.spyder-ide.org
[python-docs]: https://www.python.org/doc
[pandas-docs]: https://pandas.pydata.org/pandas-docs/stable/
[so-python]: https://stackoverflow.com/questions/tagged/python?tab=Votes
[python-mailing-lists]: https://www.python.org/community/lists
[pypi]: https://pypi.org/
[python-guide]: https://docs.python-guide.org
[dive-into-python3]: https://diveintopython3.net/


## Key Points

- Python is an open source and platform independent programming language.
- Jupyter Notebooks are great tools to code in and interact with Python. With the large Python community it is easy to find help on the internet.

## Acknowledgment

The material for this workshop series was created from the [Data Analysis and Visualization in Python for Ecologists](https://datacarpentry.github.io/python-ecology-lesson/) curriculum developed by [The Data Carpentry Foundation](https://datacarpentry.org/) of [The Carpentries](https://carpentries.org/) licensed under [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/)