
![index](https://user-images.githubusercontent.com/106934852/185226294-d1bd3b02-9ef0-4d65-91e6-932fdb63e237.png)
# Git & GitHub Commands

  ### SETUP
  - git config --global user.name
  - git config --global user.email
  - git config --global color.ui auto
  
  ### SETUP & INIT
  - git init : initialize an existing directory as a Git repository
  - git clone [url] : retrieve an entire repository from a hosted location via URL
  
  ### STAGE & SNAPSHOT
 - git status : show modified files in working directory, staged for your next commit
- git add [file] : add a file as it looks now to your next commit (stage)
- git reset [file] : unstage a file while retaining the changes in working directory
- git diff : diff of what is changed but not staged
- git diff --staged : diff of what is staged but not yet commited
- git commit -m “[descriptive message]” : commit your staged content as a new commit snapshot

### BRANCH & MERGE
- git branch : list your branches. a * will appear next to the currently active branch
- git branch [branch-name] : create a new branch at the current commit
- git checkout : switch to another branch and check it out into your working directory
- git merge [branch] : merge the specified branch’s history into the current one
- git log : show all commits in the current branch’s history

### INSPECT & COMPARE
- git log : show the commit history for the currently active branch
- git log branchB..branchA : show the commits on branchA that are not on branchB
- git log --follow [file] : show the commits that changed file, even across renames
- git diff branchB...branchA : show the diff of what is in branchA that is not in branchB
- git show [SHA] : show any object in Git in human-readable forma

### TRACKING PATH CHANGES
- git rm [file] : delete the file from project and stage the removal for commit
- git mv [existing-path] [new-path] : change an existing file path and stage the move
- git log --stat -M : show all commit logs with indication of any paths that moved 

### IGNORING PATTERNS
```
<sub> logs/
*.notes
pattern*/  
```
:Save a file with desired paterns as .gitignore with either direct string matches or wildcard globs
- git config --global core.excludesfile [file] : system wide ignore patern for all local repositories

### SHARE & UPDATE
- git remote add [alias] [url] : add a git URL as an alias
- git fetch [alias] : fetch down all the branches from that Git remote
- git merge [alias]/[branch] : merge a remote branch into your current branch to bring it up to date
- git push [alias] [branch] :Transmit local branch commits to the remote repository branch
- git pull : fetch and merge any commits from the tracking remote branch

### REWRITE HISTORY
- git rebase [branch] : apply any commits of current branch ahead of specified one
- git reset --hard [commit] : clear staging area, rewrite working tree from specified commit

### TEMPORARY COMMITS
- git stash : Save modified and staged changes
- git status list : list stack-order of stashed file changes
- git stash pop : write working from top of stash stack
- git stash drop : discard the changes from top of stash stack


## Git Branch 
 - This document is an in-depth review of the git branch command and a discussion of the overall Git branching model. Branching is a feature available in most modern version control systems. Branching in other VCS's can be an expensive operation in both time and disk space. In Git, branches are a part of your everyday development process. Git branches are effectively a pointer to a snapshot of your changes. When you want to add a new feature or fix a bug—no matter how big or how small—you spawn a new branch to encapsulate your changes. This makes it harder for unstable code to get merged into the main code base, and it gives you the chance to clean up your future's history before merging it into the main branch.
 
![Screenshot (216)](https://user-images.githubusercontent.com/106934852/185224858-63892eca-d0da-4013-869e-b6d7424b5911.png)

## Git Index
- The Git index is a staging area between the working directory and repository. It is used to build up a set of changes that you want to commit together. To better understand the Git index, then first understand the working directory and repository.

![git](https://user-images.githubusercontent.com/106934852/185226337-db2161a2-4709-42e3-b744-74e279234ec4.png)

### Working directory:
- When you worked on your project and made some changes, you are dealing with your project's working directory. This project directory is available on your computer's filesystem. All the changes you make will remain in the working directory until you add them to the staging area.
### Staging area:
- The staging area can be described as a preview of your next commit. When you create a git commit, Git takes changes that are in the staging area and make them as a new commit. You are allowed to add and remove changes from the staging area. The staging area can be considered as a real area where git stores the changes.
###  Repository:
- repository is like a data structure used by VCS to store metadata for a set of files and directories. It contains the collection of the files as well as the history of changes made to those files. Repository in Git is considered as your project folder. A repository has all the project-related data

###  Difference between forking and cloning in Git:
## Forking:
 - Forking creates your own copy of a repository in a remote location (for example, GitHub). Your own copy means that you will be able to contribute changes to your copy of the repository without affecting the original repository.
 ## cloning:
 - Cloning makes a local copy of a repository, not your own copy. Think of it as downloading a repository onto your local hard drive. Unlike forks, clones have references to their original repositories.
 
 ![Screenshot (221)](https://user-images.githubusercontent.com/106934852/186707028-caeb04c6-0370-4886-9de9-d6e7cec0d292.png)

### 
