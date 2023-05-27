---
title: Version control. Git.

# Summary for listings and search engines
summary: Version control. Git.

# Link this post with a project
projects: []

# Date published
date: '2023-03-18T00:00:02Z'

# Date updated
lastmod: '2023-03-18T00:00:02Z'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/jpg` in this page's folder and customize its options here.
image:
  caption: 'Image credit: [**Unsplash**]()'
  focal_point: ''
  placement: 2
  preview_only: false

authors:
  - admin

tags:
  - Academic

categories:
  - Demo
---

```python
import libr
print('hello')
```


# **Version Control Systems.General Concepts**

**Version Control Systems (VCS)** are used when several people work on a project. Usually the main project tree is stored in a local or remote repository, to which access is set up for project members. When changes are made to the project content, version control systems allow you to commit changes, merge changes made by different project members, and revert to any earlier version of the project if needed.

Classic version control systems use a centralized model, which implies a single repository for storing files. Most version control functions are performed by a special server. A project participant (user) obtains the necessary version of the files before starting to work, and after making changes, the user places the new version into the repository, so that previous versions are not deleted from the central repository and can be returned to at any time.

Version control systems support the ability to track and resolve conflicts that may arise when several people work on the same file. You can merge changes made by different participants (automatically or manually), manually select the correct version, discard changes at all or lock files for modification. Depending on the settings, locking prevents other users from getting a working copy or prevents modification of the working copy by the OS file system, thereby ensuring that the version of the file is not changed.

Version control systems can also provide additional, more flexible functionality. For example, they can support multiple versions of the same file, keeping an overall history of changes up to the branching point and each branch's own change history. In addition, information is usually available about which participant made which changes, when, and what changes. Usually, this kind of information is stored in a change log, access to which can be restricted.

In contrast to classical VCSs, in distributed version control systems a central repository is optional.

Among the classical VCSs the most famous are CVS, Subversion, and among the distributed ones - Git, Bazaar, Mercurial, etc. The principles of their work are similar, the main difference is the syntax of the commands used.

# **The Git version control system**

**The Git version control system** is a collection of command-line programs. These can be accessed from the terminal by entering the git command with various options.

Because Git is a distributed version control system, you can back up your local repository by simply copying or archiving it.

# **Basic git commands**

The most commonly used git commands are given in the table below 

Команда Описание![](Aspose.Words.d8d007bc-3873-4168-a695-b631a7f23e98.003.jpg)

git init creating the main repository tree

git pull to retrieve updates (changes) to the current tree from the

central repository

git push push any changes you have made to the local

to the central repository

git status to browse the list of changed files in the current

directory

git diff to review the current changes

git add . add all modified and/or created files and/or

directories

git add specific modified and/or created file names and/or directories

git rm to remove the file and/or directory from the repository index (which keeps the file and/or directory in the local directory)

git commit to save any changes you've added and any changes you've changed -am 'commit file description

Command Description![](Aspose.Words.d8d007bc-3873-4168-a695-b631a7f23e98.006.jpg)

git checkout create a new branch based on the current branch -b branch name\_name

git checkout switch to some branch (switching to a branch name that isn't already in the local repository will

branch that isn't yet in the local repository is created and linked to a remote branch)

git push to send branch changes to the central origin repository

branch name

git merge branch into current tree --no-ff

branch name

git branch -D remove a local branch that has already been merged into the main branch, branch name

git branch -D forcibly deletes a local branch

branch name

git push branch removal from the central repository

origin

:name\_branches![](Aspose.Words.d8d007bc-3873-4168-a695-b631a7f23e98.005.jpg)

# **Standard procedures for working with a central repository**

The user begins by checking and getting changes from the central repository (no changes should have been made to the local tree before this procedure began):![](Aspose.Words.d8d007bc-3873-4168-a695-b631a7f23e98.004.jpg)


git checkout master

git pull

git checkout -b branch name\_name

You can then make changes to the local tree and/or branch.

When you are done making changes to files and/or directories in your project, you should place them in the central repository. To do this, you need to check which files have changed so far:

git status

and if necessary, remove unnecessary files you do not want to upload to the central repository.

Then, it is useful to review the changes against the clean commit rules:

git diff

If there are files that should be kept out of the commit, you can use the add and/or remove commands with the appropriate options to keep the changes:

git add file names git rm file names

If you want to keep all changes in the current directory, use: git add .

Then save the changes, explaining what was done:

git commit -am "Some commit message"

and push it to the central repository:

git push origin branch_name

or

git push

