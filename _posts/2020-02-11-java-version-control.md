---
layout:     post
title:      JAVA version control
subtitle:   Switch Java version in Mac OS
date:       2020-02-11
author:     Clover
header-img: img/post-bg-markdown.jpg
catalog: true
tags:
    - Skills

---

### Steps of Java version switch:
Under some situations, we need to switch from the latest java version (e.g. java11) to olders and more stable versions (e.g java8) to compile with some libraries.

##### Step1:
- Add the target java version from Oracle to local computer and check in terminal

$ `/usr/libexec/java_home -V`

<figure>
  <img src="/img/java-version-control/1.png" alt="Image" />
</figure>

- And make sure there are two or more versions in your local computer

$ `cd /Library/Java/JavaVirtualMachines`

$ `ls`

<figure>
  <img src="/img/java-version-control/2.png" alt="Image" />
</figure>

______________________________________________


##### Step2:

- Add Alias to the file ~/.bash_profile（if Zsh，edit ~/.zshrc）

```
# JDK 11  
export JAVA_11_HOME="/Library/Java/JavaVirtualMachines/11.0.1.jdk/Contents/Home"
# JDK 8
export JAVA_8_HOME="/Library/Java/JavaVirtualMachines/jdk1.8.0_241.jdk/Contents/Home"

export JAVA_HOME=$JAVA_8_HOME #default JDK 8

#alias to switch java version
alias jdk11="export JAVA_HOME=$JAVA_11_HOME"    
alias jdk8="export JAVA_HOME=$JAVA_8_HOME"  
```

<figure>
  <img src="/img/java-version-control/3.png" alt="Image" />
</figure>

- Update the file 
$ `source ~/.bash_profile`  (zsh: `source ~/.zshrc`)

<figure>
  <img src="/img/java-version-control/4.png" alt="Image" />
</figure>

______________________________________________

##### Step3:

- Make sure the java version has been switched

<figure>
  <img src="/img/java-version-control/5.png" alt="Image" />
</figure>

- Use Alias to switch java versions

<figure>
  <img src="/img/java-version-control/7.png" alt="Image" />
</figure>

______________________________________________

##### Step4:

- If use ide, make the ide use the correct JAVA version

<figure>
  <img src="/img/java-version-control/6.png" alt="Image" />
</figure>


______________________________________________

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
  ____________________________
  
- Recover your last version from master to work dict

  Very dangerous!!! You have to remember your last commit clearly!
  
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
   
