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

##### Workspace, stage and master
<figure>
  <img src="/img/git-concept.jpg" alt="Image" />
</figure>

|    name    | function |
| ---------- | --- |
|workspace|What you can see in your computer|
|stage    |Keep your files temporarily|
|master   |Keep your old version works| 

______________________________________________

##### Commands
- Create your files
 `mkdir test`
 
 `cd test`
 
 `touch hello.txt`
 
 `vi hello.txt`
 
 `touch color.txt`
 
 `vi color.txt`

- Start a new git
	
     After find your work directory
     
    `git init`

- Store your files

    `git add filename` or `git add .` to add all your file in the current directory
    
- Check git status
    `git status`
    
    Now you can see your files have added 
    
    ```

    ```
  
- Check the difference 

   If you make some change in the file hello.text
   
   `git diff`
   
   ```
 
   ```
    
- Store what in your stage to master

 `git add` writes into stage，but `git commit` writes from stage to master
 
 `git commit -m "1st submit"`

```

 ```
