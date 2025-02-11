# Git Lab Training

A training platform for users to practice in and potentially learn from.

## Getting started

Software Configuration Management (SCM) is considered the most important aspect of maintaining control over your work in the field of Computer Science / Software Engineering.  Without SCM you don't know where you are, what has transpired, when is happened, how it happened, and your put both your project and team at great unecessary risk.

Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.   Additional information can be found at the [Git] (https://git-scm.com) web site.

The section below enumerates a basic set of commands intended to help one both see the value of a SCM solution as well as provide you some insight into this SCM's solution use.

[Everyday Git](https://git-scm.com/docs/giteveryday)

## Some Concepts

In Gitlab, the web based wrapper used to manage your Git repositories, there are a few concepts that are important to recognize:

- Users - You.  An account tied to a person representing a unique identifier for that person used to manage access / security to groups, projects, and repositories.
- Groups - used to manage access control ad cluster 1 to N users into a common permissions framework.  You may have 1 to N users per project.
- Projects - used to manage clusters of repositories.  You may have 1 to N repositories per project.
- Repositories - discrete groups of files that are managed separate from other groups of files.  You will have 1 to N files within a repository.

## What's Inside

- [ ] Training (./training) - MS Powerpoint presentations originally created for FNMOC Model Operations used to help train people on Git utilization with explicit DI2E / command-line use examples.
- [ ] Cheat Sheets (./cheatsheet) - Two different cheat sheets (1-2 pagers) of concise directives on using Git.
- [ ] Manuals (./manual) - A Git manual (book) in various formats ranging from PDF to mobi (Kindle).

## Basic Training

- [ ] Clone an existing repository.

```
cd <target location on your machine that will hold the repository>
git clone git@<some url>
ls
```

You'll see a directory named `git-lab-training`.  Change directory (`cd`) into this directory and look at the contents.  This represents a new, unchanged, repository that you can start managing files with.

```
git status
git diff
```

This command (status) will show you the status of your repository and highlight any files that have changed.  Note that as this is a new repository you will see zero files appear (unless you have already changed something).

Git diff demonstrates specifically what those changes are per file.  Note that this can be overwhelming if you have a lot of changes.  This is true of the status command as well but much more so with the diff command.

- [ ] Add files to the repository.
```
date >> ./<your name>.txt
```
This command will put today's date into a text file named after you.  


- [ ] See the difference in what was there and current reality.
```
git status
git diff
```
Performing the status command will reflect this new file addition and you should see <your name>.txt appear.

The git diff command will not only show you the file you just created but the dynamics of that change with + / - sybology to reflect additions or changes.

- [ ] Commit your files and push.

Now you could keep your files here and make changes forever, but this would be no different than simply keeping them on the file system.  Sure you'd have a transactional history of change and could "go back in time" but your content would reside in this one location.  The ability for other users to collaborate and backups of your content would not be an option.  What do you do?  You "push".

```
git commit -m <provide informative reason for change>
git push
git diff
```

By performing a commit you're telling Git that you want to persist, track, and manage this change.  Comments are important and *pro tip* can be used with a log output to show what you did for the current week thus providing automatic input into your status reports.

This change isn't permanent though.  Remember that this Git repo is a localized database and doesn't represent the "final" version of your change.  

You have to "push" your change to the origin or central Git server to ensure your final modifications are saved in the authoritative location.

The third command `git diff` will now show that there are no file modifications in your current / local repository.

- [ ] Pull for new changes from other people.

To see new changes by other collaborators perform a "pull" on the remote origin repository.  There will always exist a chance that a CONFLICT appears.  A conflict is when you have the same fiel with sufficient modifications that Git cannot easily rectify those differences and you will have to interceede yourself.

Note that persistently committing and merging, regardless of using branches, you will find very few conflict occur.

```
git pull
```
## Clear out History

Deleting the .git folder may cause problems in your git repository. If you want to delete all your commit history but keep the code in its current state, it is very safe to do it as in the following:

Checkout/create orphan branch (this branch won't show in git branch command):

```
git checkout --orphan latest_branch
```

Add all the files to the newly created branch:

```
git add -A
```

Commit the changes:

```
git commit -am "commit message"
```

Delete main (default) branch (this step is permanent):

```
git branch -D main
```

Rename the current branch to main:

```
git branch -m main
```

Finally, all changes are completed on your local repository, and force update your remote repository:

```
git push -f origin main
```

Done.

# References

+ Git Documentation [https://git-scm.com/doc]
+ Git Basics [https://opensource.com/article/22/11/git-concepts]
+ https://git-scm.com/docs/giteveryday
+ Advanced Commands [https://opensource.com/article/22/11/advanced-git-commands]
=======
# Git Lab Training

A training platform for users to practice in and potentially learn from.

## Getting started

Software Configuration Management (SCM) is considered the most important aspect of maintaining control over your work in the field of Computer Science / Software Engineering.  Without SCM you don't know where you are, what has transpired, when is happened, how it happened, and your put both your project and team at great unecessary risk.

Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.   Additional information can be found at the [Git](https://git-scm.com/) web site.

The section below enumerates a basic set of commands intended to help one both see the value of a SCM solution as well as provide you some insight into this SCM's solution use.

## Some Concepts

In Gitlab, the web based wrapper used to manage your Git repositories, there are a few concepts that are important to recognize:

- Users - You.  An account tied to a person representing a unique identifier for that person used to manage access / security to groups, projects, and repositories.
- Groups - used to manage access control ad cluster 1 to N users into a common permissions framework.  You may have 1 to N users per project.
- Projects - used to manage clusters of repositories.  You may have 1 to N repositories per project.
- Repositories - discrete groups of files that are managed separate from other groups of files.  You will have 1 to N files within a repository.

## What's Inside

- [ ] Training (./training) - MS Powerpoint presentations originally created for FNMOC Model Operations used to help train people on Git utilization with explicit DI2E / command-line use examples.
- [ ] Cheat Sheets (./cheatsheet) - Two different cheat sheets (1-2 pagers) of concise directives on using Git.
- [ ] Manuals (./manual) - A Git manual (book) in various formats ranging from PDF to mobi (Kindle).

## Basic Training

- [ ] Clone an existing repository.

```
cd <target location on your machine that will hold the repository>
git clone git@<some url>
ls
```

You'll see a directory named `git-lab-training`.  Change directory (`cd`) into this directory and look at the contents.  This represents a new, unchanged, repository that you can start managing files with.

```
git status
git diff
```

This command (status) will show you the status of your repository and highlight any files that have changed.  Note that as this is a new repository you will see zero files appear (unless you have already changed something).

Git diff demonstrates specifically what those changes are per file.  Note that this can be overwhelming if you have a lot of changes.  This is true of the status command as well but much more so with the diff command.

- [ ] Add files to the repository.
```
date >> ./<your name>.txt
```
This command will put today's date into a text file named after you.  


- [ ] See the difference in what was there and current reality.
```
git status
git diff
```
Performing the status command will reflect this new file addition and you should see <your name>.txt appear.

The git diff command will not only show you the file you just created but the dynamics of that change with + / - sybology to reflect additions or changes.

- [ ] Commit your files and push.

Now you could keep your files here and make changes forever, but this would be no different than simply keeping them on the file system.  Sure you'd have a transactional history of change and could "go back in time" but your content would reside in this one location.  The ability for other users to collaborate and backups of your content would not be an option.  What do you do?  You "push".

```
git commit -m <provide informative reason for change>
git push
git diff
```

By performing a commit you're telling Git that you want to persist, track, and manage this change.  Comments are important and *pro tip* can be used with a log output to show what you did for the current week thus providing automatic input into your status reports.

This change isn't permanent though.  Remember that this Git repo is a localized database and doesn't represent the "final" version of your change.  

You have to "push" your change to the origin or central Git server to ensure your final modifications are saved in the authoritative location.

The third command `git diff` will now show that there are no file modifications in your current / local repository.

- [ ] Pull for new changes from other people.

To see new changes by other collaborators perform a "pull" on the remote origin repository.  There will always exist a chance that a CONFLICT appears.  A conflict is when you have the same fiel with sufficient modifications that Git cannot easily rectify those differences and you will have to interceede yourself.

Note that persistently committing and merging, regardless of using branches, you will find very few conflict occur.

```
git pull
```

# References

+ Git Documentation [https://git-scm.com/doc]
+ Git Basics [https://opensource.com/article/22/11/git-concepts]
+ Advanced Commands [https://opensource.com/article/22/11/advanced-git-commands]
