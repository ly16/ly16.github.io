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

    `git init`

- Store your files

    `git add filename` or `git add .` to add all your file in the current directory
    
- check git status
    `git status`
    
    now you can see your files have added 
    
    ```
    Lilis-MacBook-Pro:hw6 liliyu$ git status
    On branch master
    Initial commit

    Changes to be committed:
    (use "git rm --cached <file>..." to unstage)

	new file:   61_1.jpg
	new file:   61_2.jpg
	new file:   STA5107 hw6.pdf
	new file:   hw6.m
	new file:   hw6.pdf
    ```
    
    


