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

### fast pow of large number [positive only](https://leetcode.com/problems/minimum-non-zero-product-of-the-array-elements/)

```java
    public long multi(long base, long time) {
        if (time == 0) {
            return 1;
        }
        if (time == 1) {
            return base;
        }
        long half = multi(base, time / 2);
        long p = (half * half) % mod;
        return time % 2 == 0 ? (half * half) % mod : ((half * half) % mod * (base % mod)) % mod;
    }
```

###  min number of [add](https://leetcode.com/problems/minimum-add-to-make-parentheses-valid/) / [remove](https://leetcode.com/problems/remove-invalid-parentheses/) / [swap](https://leetcode.com/problems/minimum-number-of-swaps-to-make-the-string-balanced/) to make valid parentheses

```java
    public int minAddToMakeValid(String s) {
        int forward = 0;
        int res = 0;
        for (char c : s.toCharArray()) {
            if (c == '(') {
                forward++;
            } else {
                forward--;
                if (forward == -1) {
                    res++;
                    forward = 0;
                }
            }
        }
        res += forward;
        return res;
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
- If input list is not sorted, the results are undefined.
- If there are duplicates, there is no guarantee which one will be found.


