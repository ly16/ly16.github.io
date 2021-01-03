---
layout:     post
title:      LeetCode Appendix
subtitle:   check isPowerOfTwo, check valid tree (check cycle in undirected graph)
date:       2021-01-02
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---

### isPowerOfTwo in Java

```java
public boolean isPowerOfTwo(int n) 
{ 
    if (n == 0) 
        return false; 
    while (n != 1) 
    { 
        if (n % 2 != 0) 
            return false; 
        n = n / 2; 
    } 
    return true; 
} 
```

### check valid tree (check cycle in undirected graph)

- If we know the total node of tree:
  - if n - 1 != # of edge, there is cycle
  
- If we do not know the total node of tree:
  - Each node at most has 3 neighbors (1 parent + 2 child)

