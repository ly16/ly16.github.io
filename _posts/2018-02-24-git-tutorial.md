---
layout:     post
title:      Git Tutorial (转载+总结)
subtitle:   Git concepts and steps
date:       2018-02-24
author:     Clover
header-img: img/post-bg-markdown.jpg
catalog: true
tags:
    - Skills

---

### Start your git following instructions below

##### Work dict, stage and master
<figure>
  <img src="/img/git-concept.jpg" alt="Image" />
</figure>

|    name    | function |
| ---------- | --- |
|work dict|What you can see in your computer|
|stage    |Keep your files temporarily|
|master   |Keep your old version works| 

______________________________________________

##### Commands
- Create your files
   `mkdir test` to create a new directory
 
   `cd test` 
 
   `touch hello.txt` to create new file
 
   `vi hello.txt`  to edit

- Start a new git
	
     After find your work directory
     
    `git init`

- Store your files

    `git add filename` or `git add .` to add all your file in the current directory
    
- Check git status
    `git status`
    
    Now you can see your files have added 
    
    ```
    On branch master

    Initial commit

   Changes to be committed:
   (use "git rm --cached <file>..." to unstage)

	new file:   color.txt
	new file:   hello.txt
	new file:   touch
    ```
  
- Check the difference 

   If you make some change in the file hello.text
   
   `git diff`  difference between work dict and stage
   
   ```
  diff --git a/color.txt b/color.txt
  index d30c108..2e0df5d 100644
  --- a/color.txt
  +++ b/color.txt
  @@ -1 +1 @@
  -Red
  +Red, pink
   ```
   
    `git diff --cached` difference between stage and master
    
    `git diff HEAD --` difference between work dict and master
    
    ```
    diff --git a/color.txt b/color.txt
    index d30c108..2e0df5d 100644
    --- a/color.txt
    +++ b/color.txt
    @@ -1 +1 @@
   -Red
   +Red, pink
   ```
- Store what in your stage to master

  `git add` writes into stage，but `git commit` writes from stage to master
 
  `git commit -m "1st submit"`

  ```
  [master (root-commit) 39ebede] 1st submit
  3 files changed, 2 insertions(+)
  create mode 100644 color.txt
  create mode 100644 hello.txt
  create mode 100644 touch
  ```
  
- To restore all those deleted files 
  `git ls-files -d | xargs git checkout --`
 
- To remove the git from project directory
  `rm -rf .git`
  
- Log 

  `git log`
  
  ```
  commit 39ebededfa95f30b777bd1c257079d86fe824a6b (HEAD -> master)
  Author: yuliliclover <yuliliclover@gmail.com>
  Date:   Sun Feb 25 00:38:10 2018 -0500

    1st submit
  ```

- Cancel those in __stage__ from being committed to __master__
  
  I made change in two files, but just commit one to the master
  
  `git status -s`
  
  
  ```
  M color.txt
  M hello.txt
  ```

  ` git add .`
  
  `git status`
  
  ```
  On branch master
  Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   color.txt
	modified:   hello.txt
   ```
   
   `git reset HEAD -- color.txt`  to cancel this commit to master
   
   ```
   Unstaged changes after reset:
   M	color.txt
   ```
   
   `git status -s`
   
   ```
    M color.txt
  M  hello.txt
  ```
  
  `git commit -m "change"`
  
  ```
  [master 0cf29e4] change
  1 file changed, 1 insertion(+), 1 deletion(-)
  ```
  
  `git log`
  
  ```
  Author: yuliliclover <yuliliclover@gmail.com>
  Date:   Sun Feb 25 00:59:53 2018 -0500

    change

  commit 39ebededfa95f30b777bd1c257079d86fe824a6b
  Author: yuliliclover <yuliliclover@gmail.com>
  Date:   Sun Feb 25 00:38:10 2018 -0500

    1st submit
  ```
  
  
- Recover your last version from master to work dict
  
      __Very dangerous!!!__ You have to remember your last commit clearly!
  
     `git diff`
  
     ```
     diff --git a/color.txt b/color.txt
     index d30c108..b08fdac 100644
     --- a/color.txt
     +++ b/color.txt
     @@ -1 +1 @@
     -Red
     +Red, pink, blue
     diff --git a/hello.txt b/hello.txt
     index 8d6e1e9..716319a 100644 
     --- a/hello.txt
     +++ b/hello.txt
     @@ -1 +1 @@
      -Hello World! Goodbye!
     +Hello World! Goodbye!jhdsoi[oaidhhcoiajiojeoijr
     ```
  
  
     `git checkout hello.txt`  only recover this file from last commit
  
     `git diff`
  
    
     ```
     diff --git a/color.txt b/color.txt
     index d30c108..b08fdac 100644
     --- a/color.txt
     +++ b/color.txt
     @@ -1 +1 @@
     -Red
     +Red, pink, blue
     ```
 
- Revert to previous version

   `git reflog` to see all your changes
   
   ```
   7780f1f (HEAD -> master) HEAD@{0}: commit: change2
   39ebede HEAD@{1}: reset: moving to HEAD~1
   0cf29e4 HEAD@{2}: commit: change
   39ebede HEAD@{3}: commit (initial): 1st submit
   ```
   
   You should keep the first number according to your commit msg
   
   Say you want to return "change"
   
   `git reset --hard 0cf29e4`
   
   ```
   HEAD is now at 0cf29e4 change
   ```
   
