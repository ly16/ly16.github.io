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

- If use ide, make sure the ide use the correct JAVA version

<figure>
  <img src="/img/java-version-control/6.png" alt="Image" />
</figure>


Thanks to the reference in Chinses: https://segmentfault.com/a/1190000013131276
