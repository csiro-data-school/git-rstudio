---
layout: episode
title: Collaborative notetaking
teaching: 0
exercises: 60
objectives:
  - To practice working with Git and a remote repository
keypoints:
  - "Commit and push often to have a meaningful backup of your work"
  - "Make your commit messages meaningful"
---

To practice the interactions learned today, we will collect our notes on Git into a single repository.
While this is an example of how to collaborate using Git/GitHub, we won't be taking advantage of *all* 
the collaborative features of Git because we will **not** be editing each other's files. 

Most of the  errors you are likely to encounter with Git will arise when trying to deal with 
conflicting changes made by two people to the same file. Learning how to merge conflicting commits
in this situation is more than we can cover in one day and so we will avoid the situation.

> ## Challenge: Work together
> Create a new project that clones the [Course notes](https://github.com/csiro-data-school/focus-course-notes) repo
> 
> Under the `git` folder, you will see folders for a range of topics/commands.
>
> Record your notes from the session in the relevant folders. Save the files as `<YOUR_NAME>-notes.txt`
> to avoid conflicts with other participant's notes.
>
> Remember to commit and push at appropriate points.
>
> Pull changes from the remote repo to see your classmates notes.
{:.challenge}

> ## Warning
> With lots of people pushing to a repository at once, you will encounter some issues that don't occur often in 
> day to day usage. Git will not let you push to a remote repository if someone has already pushed their own changes
> to it. If you try, you might see an error like this:
>
> ~~~~~~
> To https://github.com/USERNAME/REPOSITORY.git
>  ! [rejected]        master -> master (non-fast-forward)
> error: failed to push some refs to 'https://github.com/USERNAME/REPOSITORY.git'
> To prevent you from losing history, non-fast-forward updates were rejected
> Merge the remote changes (e.g. 'git pull') before pushing again.  See the
> 'Note about fast-forwards' section of 'git push --help' for details.
> ~~~~~
> {: .output}
> In order to correct this, you will need to first get the new changes from the remote repository on to your own
> computer, before sending your changes to GitHub.
>
> The error message gives you a hint in how to do this:
>
> - First **pull** any new changes from GitHub onto your computer
> - Then **push** the most up to date files, along with your new changes, to GitHub
>
{: .discussion}

> ## Challenge: Know your tools
> Today we have introduced you to three new tools: 
>
> - Git
> - GitHub
> - RStudio
>
> Write a short paragraph on each of these describing what each tool does, and how they interact with each other.
> Commit it to our notes repository in the `tools` folder.
{: .challenge}

