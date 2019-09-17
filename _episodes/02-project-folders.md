---
layout: episode
title: Project directories
teaching: 15
exercises: 20
questions:
  - How should I organise my project files?
objectives:
  - Understand the key features of a project directory
  - Design a project structure that separates components logically
keypoints:
  - Project directories should contain a single self-contained unit of work
  - Clear and logical organisation and naming aids understanding of the project
---

> ## Challenge 1 - understanding your filesystem
>
> Download [this data file]({{ page.root }}{% link data/gapminder.csv %}) and save it on your computer.
> 
> Files on your computer are stored in a kind of 'heirachy' or 'tree' structure called a **filesystem**. 
> 
> On a piece of paper, using windows explorer (or any other tool of your choice), 
> make a drawing that represents the location of your file on your computer. 
>
> > ## Solution
> > An example might be:
> > 
> > "Users" folder -> "stephen" folder -> "Downloads" folder -> "gapminder.csv" file
> {: .solution}
{: .challenge}

If the previous lesson provided a *bad* example of project organisation, what would a good one look 
like? The specifc answer will depend on your project, but general idea is that someone else (probably
yourself in six months) should be able to look at your project and understand what everything does.
Some good principles to help achieve this can be found in [Good Enough Practices for Scientific Computing](https://github.com/swcarpentry/good-enough-practices-in-scientific-computing/blob/gh-pages/good-enough-practices-for-scientific-computing.pdf)
and [A Quick Guide to Organising Computational Biology Projects](https://doi.org/10.1371/journal.pcbi.1000424).

> ## Challenge 2
> 
> Look at the example from Figure 1 of A Quick Guide to Organising Computational Biology Projects.
> The large text shows folder names and the smaller text file names.
> ![](https://journals.plos.org/ploscompbiol/article/figure/image?download&size=large&id=info:doi/10.1371/journal.pcbi.1000424.g001){:width="50%"}
> Can you explain the purpose of each folder and file?
>
{: .challenge}


Some specific recommendations to help achieve this goal are the following. Feel free to use them if 
they work for your projects.

### Put each project in its own directory, which is named after the project.

All the files necessary for the project should be kept within this directory, and no unnecessary 
files should be kept here. This means that the project directory is a self-contained unit of analysis
easily able to be backed up, transferred or managed without having to worry about the state of other 
files elsewhere on the computer.

### Put text documents associated with the project in a `doc` directory.

This location stores long form text documents describing and documenting the project as a whole. It 
is also a good place to store documents that start to interpret the results of a project, such as
the preparation of a manuscript for publication.

### Put raw data and metadata in the `data` directory, 

The raw data you use for a project should be be considered read only and not modified. If there are
steps required for data processing and cleaning, make sure to document those steps carefully (learning
to script your data processing will help here) and store the cleaned data separately (perhaps in a 
`derived_data` directory) 

### Put files generated during analysis in a `results` directory.

Anything that could be considered output of our analysis goes in the results folder. Examples of 
files that might go here include figures, modelling output, summarised data tables, etc.

### Put source for the project's scripts and programs in the `src` directory, and programs brought in from elsewhere or compiled locally in the `bin` directory.

This distinction is most relevant when you are both writing your own code, as well as using external
programs in an analysis. For most simple projects however, you can make do with a single `scripts`
folder that stores your analysis code.

### Name all files to reflect their content or function.

It's no use having a sensible directory structure if your files are named cryptically. When you look
back on the project in the future, `fig1.png` will likely be meaningless and you will have to open 
several files to find the one you are after. Instead, a name like `weight_comparison_plot.png` makes
it very clear what the file contains, allowing you to find the relevand file faster.

> ## Challenge 3
> 
> Sketch out a proposed project directory for one of your own projects. Include some example file 
> names that you would create in the course of the analysis.
{: .challenge}
