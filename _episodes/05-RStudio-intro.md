---
title:   Introduction to R and R Studio 
teaching: 20
exercises: 10
questions:
- "How do you find your way around RStudio?"
- "How do you interact with R?"
objectives:
- "Describe the purpose and use of each pane in the RStudio IDE"
- "Locate buttons and options in the RStudio IDE"
- "Manage a workspace in an interactive R session"
- "Manage packages"
keypoints:
- "Use RStudio to write and run R programs."
- "Set up an RStudio project for each analysis you are performing."
source: Rmd
---

## Introduction to RStudio

We'll be using RStudio: a free, open source R integrated development
environment. It provides a built in editor, works on all platforms (including
on servers) and provides many advantages such as integration with version
control and project management.


**Basic layout**

When you first open RStudio, you will be greeted by three panels:

  * The interactive R console/terminal (entire left)
  * Environment/History (tabbed in upper right)
  * Files/Plots/Packages/Help/Viewer (tabbed in lower right)

![RStudio layout]({{ site.baseurl }}/fig/05-rstudio-layout.png)

Once you open files, such as R scripts, an editor panel will also open
in the top left.

![RStudio layout with .R file open]({{ site.baseurl }}/fig/05-rstudio-layout-script.png)

You can move the panels around in RStudio so that their arrangement suits you.

# Projects

R Studio provides in-built support for keeping all files associated with a project 
together.  This includes the input data, R Scripts, analytical results and figures.

A good project layout will ultimately make your life easier:

* It will help ensure the integrity of your data;
* It makes it simpler to share your code with someone else
(a lab-mate, collaborator, or supervisor);
* It allows you to easily upload your code with your manuscript submission;
* It makes it easier to pick the project back up after a break.


> ## Challenge: Creating a self-contained project
>
> We're going to create a new project in RStudio:
>
> 1. Click the "File" menu button, then "New Project".
> 2. Click "New Directory".
> 3. Click "New Project".
> 4. Type in the name of the directory to store your project, e.g. "intro-git".
> 5. Select "Create a git repository"
> 6. Click the "Create Project" button.
{: .challenge}

Now when we start R in this project directory, or open this project with RStudio,
all of our work on this project will be entirely self-contained in this directory.

The two main changes after creating and opening a project are the progect menu and the Git information
pane. Both highlighted here:

![]({{ site.baseurl }}/fig/05-rstudio-git-project.png)
