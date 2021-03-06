---
layout:     post
title:      LeetCode Appendix
subtitle:   Formular of useful algorithm
date:       2021-01-02
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---
### GCD of two numbers 辗转相除法 Euclidean algorithm

```java
public int gcd(int a, int b) {
    if (a > b) {
        return b == 0 ? a : gcd(b, a % b);
    } else {
        return a == 0 ? b : gcd(a, b % a);
    }
}
```


### LCM (Least Common Multiple) of two numbers: a, b
```
GCD * LCM = a * b
```


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
  
  
### Arrays.binarySearch() Java API
- It returns the insertion point of the index = -(res + 1)
- Similar to Collections.binarysearch() in list or other collections.

> If input list is not sorted, the results are undefined.

> If there are duplicates, there is no guarantee which one will be found.


