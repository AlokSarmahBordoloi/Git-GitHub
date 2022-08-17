# Git Commands

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
