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
// recursive version
public int gcd(int a, int b) {
    if (b == 0) {
        return a;
    }
    return gcd(b, a % b);
}

// iterative version
int findGCD(int n1, int n2) {
    while (n1 != 0) {
        int temp = n1;
        n1 = n2 % n1;
        n2 = temp;
    }
    return n2;
}
```


### LCM (Least Common Multiple) of two numbers: a, b
```
GCD * LCM = a * b
```

### find all the prime number <= n

```java
public List<Integer> findSmallerPrime(int n) {
    int[] array = new int[n + 1];
    for (int i = 2; i * i <= n; i++) {
        int multi = i * 2;
        while (multi <= n) {
            array[multi] = 1;
            multi += i;
        }
    }
    List<Integer> res = new ArrayList<>();
    for (int i = 2; i <= n; i++) {
        if (array[i] == 0) {
            res.add(i);
        }
    }
    return res;
}
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
        return time % 2 == 0 ? (half * half) % mod : ((half * half) % mod * (base % mod)) % mod;
    }
```

### fast pow of number (positive/negative)
```java
class Solution {
    public double myPow(double x, int n) {
        if (n >= 0) {
            return dfs(x, n);
        }
        return 1.0 / dfs(x, -n);
    }
    
    public double dfs(double x, int n) {
        if (n == 0) {
            return 1.0;
        }
        double y = dfs(x, n / 2);
        return n % 2 == 0 ? y * y : y * y * x;
    }
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

### tree map api

```java
public static void main(String[] args) {
    TreeMap<Integer, Integer> map = new TreeMap<>();
    map.put(3, 2);
    map.put(5, 7);
    map.put(9, 11);
    map.put(2, 6);
    System.out.println(map.firstKey()); // 2
    System.out.println(map.descendingKeySet()); // [9, 5, 3, 2]
    System.out.println(map.floorKey(6)); // 5
    System.out.println(map.ceilingKey(100)); // null
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


