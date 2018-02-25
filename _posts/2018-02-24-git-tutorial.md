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

- Start a new git
	
     After find your work directory
     
    `git init`

- Store your files

    `git add filename` or `git add .` to add all your file in the current directory
    
- Check git status
    `git status`
    
    Now you can see your files have added 
    
    ```
    Lilis-MacBook-Pro:test liliyu$ git status
    On branch master

    Initial commit

    Changes to be committed:
    (use "git rm --cached <file>..." to unstage)

	new file:   Weekend.text
	new file:   hello.text
    ```
  
- Check the difference 

   If you make some change in the file hello.text
   
   `git diff`
   
   ```
   diff --git a/hello.text b/hello.text
   deleted file mode 100644
  index 633c679..0000000
  --- a/hello.text
  +++ /dev/null
  @@ -1,8 +0,0 @@
  -{\rtf1\ansi\ansicpg1252\cocoartf1504\cocoasubrtf830
  -{\fonttbl\f0\fswiss\fcharset0 Helvetica;}
  -{\colortbl;\red255\green255\blue255;}
  -{\*\expandedcolortbl;;}
  -\paperw11900\paperh16840\margl1440\margr1440\vieww10800\viewh8400\viewkind0
  -\pard\tx566\tx1133\tx1700\tx2267\tx2834\tx3401\tx3968\tx4535\tx5102\tx5669\tx6236\tx6803\pardirnatural\partightenfactor0
  -
  -\f0\fs24 \cf0 Hello World!}
  \ No newline at end of file
   ```
    


