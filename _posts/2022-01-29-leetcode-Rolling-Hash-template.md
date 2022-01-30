---
layout:     post
title:      LeetCode Rolling Hash template
subtitle:   Rolling Hash templates in Java and relevant questions
date:       2022-01-29
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---

#### Rolling Hash
- time = O(n)
- space = O(1)

```java
public static void main(String[] args) {
    String s = "abcdefg";
    String t = "bcd";

    int mod = 1_000_000_007;
    int p = 26;
    long target = 0;
    for (int i = 0; i < t.length(); i++) {
        target = (target * p % mod+ (t.charAt(i) - 'a')) % mod;
    }

    long mul = 1;
    for (int i = 1; i < t.length(); i++) {
        mul = mul * p % mod;
    }
    int n = s.length();
    long sum = 0;
    for (int i = 0; i < n; i++) {
        if (i >= t.length()) {
            sum = (sum - (s.charAt(i - t.length()) - 'a') * mul % mod + mod) % mod;
        }
        char ch = s.charAt(i);
        sum = (sum * p % mod + (ch - 'a')) % mod;
        if (i >= t.length() - 1) {
            if (target == sum) {
                System.out.println(s.substring(i - t.length() + 1, i + 1));
            }
        }
    }
}
```

#### 2156. Find Substring With Given Hash Value
反向的rolling hash

- time = O(n)
- space = O(1)

```java
class Solution {
    public String subStrHash(String s, int power, int mod, int k, int hashValue) {
        int n = s.length();
        long sum = 0;
        
        long maxPow = 1;
        for (int i = 1; i < k; i++) {
            maxPow = (maxPow % mod * power % mod) % mod;
        }
        
        String res = "";
        for (int i = n - 1; i >= 0; i--) {
            if (i + k - 1 < n - 1) {
                int rightValue = s.charAt(i + k) - 'a' + 1;
                sum = (sum - rightValue * maxPow % mod + mod) % mod;
            }
            
            int cValue = s.charAt(i) - 'a' + 1;
            sum = (sum * power % mod + cValue) % mod;
            if (i + k - 1 <= n - 1) {
                if (sum == hashValue) {
                    res = s.substring(i, i + k); 
                }
            }
        }
        return res;
    }
}
```


#### Relevant questions & reference

* https://leetcode.com/problems/find-substring-with-given-hash-value/

