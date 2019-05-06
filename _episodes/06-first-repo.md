---
layout: episode
title: Our first repo 
teaching: 30
exercises: 30
questions:
  - What is a repository?
  - How does Git operate?
  - How do I make commits?
  - How do I select what to commit?
objectives:
  - Learn to create Git repositories and make commits.
  - Get a grasp of the structure of a repository.
  - Learn how to inspect the project history.
  - Learn how to write useful commit log messages.
keypoints:
  - "Initializing a Git repository is simple: `git init`"
  - Commits should be used to tell a story.
  - Git uses the .git folder to store the snapshots.
---

## Tracking a guacamole recipe with Git

We will learn how to initialize a Git repository, how to track changes, and how
to make delicious guacamole!

This example is inspired by [Byron Smith](http://blog.byronjsmith.com), for original reference, see
[this thread](http://lists.software-carpentry.org/pipermail/discuss/2016-May/004529.html).
The motivation for taking a cooking recipe instead of a program is that everybody can relate to cooking
but not everybody may be able to relate to a program written in e.g. Python or another language.

Let's start.

We have already created a new project and initialised a git repository. This is all that is needed 
to start tracking our work.

One of the basic principles of Git is that it is **easy to create repositories**:

If we look at the directory's contents, it doesn't seem like much has happened. All we can see so far
is a `.gitignore` file (which tells Git if there are any files we don't want tracked) and a 
`intro-git.Rproj` file (which is an RStudio created file that stores Rstudio settings)

But if we ask to see hidden files as well ("More" > "Show Hidden Files"), we can see that Git has 
created a hidden directory within `intro-git` called `.git`:  

Git uses this special sub-directory to store all the information about the project, including all 
files and sub-directories located within the project’s directory. If we ever delete the .git 
sub-directory, we will lose the project’s history.

We can monitor what is going on with the repository using the Git pane:

![](/fig/05-rstudio-git-project.png)

We will learn how to make sense of this information during this lesson.


## So what exactly is a Git repository?

- Remember Git is a *version control system*: it records snapshots and tracks the contents of a folder as it changes over time.
- Every time we **commit** a snapshot, Git records a snapshot of the **entire project**, saves it, and assigns it a version.
- These snapshots are kept inside the `.git` sub-folder.
- If we remove `.git`, we remove the repository and history (but keep the working directory!).
- `.git` uses relative paths - you can move the whole thing somewhere else and it will still work
- Git doesn't do anything unless you ask it to (it does not record anything automatically).

---

## Recording a snapshot with Git

- Git takes snapshots only if we request it.
- We will record changes always in two steps (we will later explain why this is a recommended practice):
- We first focus (we "stage" the change), then shoot (commit the changes to the repository):

![Git staging]({{ site.baseurl }}/fig/git_stage_commit.svg
"git staging and committing"){:class="fig-responsive" style="max-width:70%"}

> ## Discussion
>
> What do you think will be the outcome if you stage a file and then edit it and stage it again, do this
> several times and at the end perform a commit? (think of focusing several scenes and pressing the shoot
> button only at the end)
{: .discussion}

---

So that's the concept - let's do it for real.

Let's **create two files**.

One file is called `instructions.txt` and contains:

```
* chop avocados
* chop onion
* squeeze lime
* add salt
* and mix well
```

The second file is called `ingredients.txt` and contains:

```
* 2 avocados
* 1 lime
* 2 tsp salt
```

> ## Challenge 1
>
> Create the files `instructions.txt` and `ingredients.txt` with "File" > "New File" > "Text File"
> 
> Add the contents above and save the files. 
{: .challenge}

As mentioned above, you can always check the status of files in your repository using
the Git pane. It provides information about what git knows about the files you are working on. The 
left hand "Status" column shows the status of any staged changes, while the right hand column shows 
the status of the actual files in our directory. The status shown is in relation to the last known state
of the file in the Git repository.

![](/fig/06-status.png)

The two files are currently untracked by Git (shown by the "?" symbols). This means that Git can 
see that the files exist in our directory, but has not been told to keep track of them.
Going back to the photography analogy, you want to **add the files** (focus the camera)
to the list of files tracked by Git. Git does not track any files automatically and you need make a 
conscious decision to add a file. To add the files to Git, simply select the check mark in the 
"Staged" column:

![](/fig/06-staged.png)

You will see that the status of these files now switches to **[A]**dded in the left hand column.
Now this change is *staged* and ready to be committed (the camera is focused and we're ready to take the snapshot).

Let's now commit the change to the repository using the "Commit" menu:

![](/fig/06-commit.png){:width="70%"}

This menu provides information about the staged changes and lets us stage additional changes if needed.
In order to actually commit a change to the Git repository, we first need to provide a commit message
that describes the changes we are making. This message should be a short (usually one line) explanation
that tells us what the major effects of this commit are. 

For this commit, add a message like "adding ingredients and instructions" and confirm the "Commit".
Git will then provide some information on exactly what it has done:
![](/fig/06-commit-confirm.png)

### Looking at the history

To see what information Git has stored about your snapshot, we can look at the history tab (![](/fig/06-history-tab.png){:width="8%"}{:style="display: inline;"})

![](/fig/06-history.png){:width="50%"}


- We can browse the development and access each state that we have committed.
- The SHA hash value uniquely labels a state of the files.

---

> ## Challenge 3
>
> Add 1/2 onion to `ingredients.txt` and also the instruction
> "enjoy!" to `instructions.txt`. Save the files, but do not stage the changes yet.
>
> How does the status of the files change? Hover over the status symbol if you do not understand what
> it means.
> 
> Have a look at the output of the "Diff" tab (![](/fig/06-diff-tab.png){:width="8%"}{:style="display: inline;"}).
> What does it tell us about the files?
>
> > ## Solution to Challenge 3
> >
> > The status of the two files changes to **[M]**odified. Because it is in the right hand column, 
> > these modifications are in our working directory. The changes have not yet been staged.
> > 
> > ![](/fig/06-diff.png){:width="50%"}
> > The Diff tab shows any changes in the file since the last commit. Red lines have been removed,
> > while green lines have been added.
> {: .solution}
{: .challenge}

> ## Challenge 4
> 
> Stage and commit each change separately. For the second commit, provide a long commit message with
> multiple lines of text.
> 
> What does the Git history look like after the two commits? What has happened to the second commit message?
> 
> > ## Solution to Challenge 4
> > 
> > An example history pane:
> > ![](/fig/06-history-long-commit.png){:width="50%"}
> > The provided commit message was:
> > ~~~~~
> > Reminding everyone to stop and smell the roses.
> > It's important to specify enjoying the food in the instructions because otherwise people might not like the taste.
> > And we really want people to enjoy this one.
> > ~~~~~
> > Only the first line is shown in the history, but the entire message *does* get recorded in the 
> > commit and can be seen if you use command line tools
> {: .solution}
{: .challenge}


### Writing useful commit messages

Looking at the history we can see that the first line of the commit message is very important.

Good example:

```
increase threshold alpha to 2.0

the motivation for this change is
to enable ...
...
```

Convention: **one line summarizing the commit, then one empty line,
then paragraph(s) with more details in free form, if necessary**.

- Bad commit messages: "fix", "oops", "save work", "foobar", "toto", "qppjdfjd", "".
- For your amusement: [http://whatthecommit.com](http://whatthecommit.com)
- Write commit messages in English that will be understood
  15 years from now by someone else than you.

---

## Ignoring files and paths with `.gitignore`

Some files should not be tracked in a Git repository. This includes files that are:
- specific to a particular computer
- contain sensitive information
- large, binary files
- compiled files

> ## Discussion
> 
> What could be the problems raised by committing the above files to a repo?
{: .discussion}


For this we use `.gitignore` files. Example:

```
# ignore R binary files 
*.RData
# ignore .exe files
*.exe
```

> ## Challenge 5
> 
> Make a new file called `my-personal-notes.txt`. Add some content to the file that describes your feelings about Git so far...
> 
> Since you might not want these comments seen by collaborators, make sure it is ignored by git
> 
> > ## Solution to Challenge 5
> > 
> > By adding the path `my-personal-notes.txt` to the `.gitignore` file, your personal thoughts about Git won't be added to any snapshots.
> {: .solution}
{: .challenge}

You can have `.gitignore` files in lower level directories and they affect the paths
relatively.

`.gitignore` should be part of the repository (why?).


### Keep your repo clean

- Check the status window a lot to keep track of what Git is doing.
- Use `.gitignore`.
- If you don't want to track a file, it should be listed in .gitignore.
- **All files should be either tracked or ignored**.

---

## Summary

Now we know how to save snapshots (commits):

1. Make changes to a file (working directory modified, staging and repository same as last commit).

2. Tell Git we would like to stage the changes (Staging area now modified, ready to commit).

3. Commit the changes we have staged with a message that explains them (working directory, staging, 
and the repository now all up to date with new changes. Repository tracks the history of the changes
as well).

And this is what we do as we program.

Every state is then saved and later we will learn how to go back to these "checkpoints"
and how to undo things.
