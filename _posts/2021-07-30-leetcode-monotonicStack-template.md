---
layout:     post
title:      LeetCode Monotonic stack template
subtitle:   Monotonic stack in Java and relevant questions
date:       2021-07-30
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---

### Java Template
Use Stack or Deque for array, Keep an ascending or descending order

- time = O(n)
- space = O(n)

[Leetcode 1947. Maximum Compatibility Score Sum](https://leetcode.com/problems/maximum-compatibility-score-sum/)

```java
class Solution {
    public int maxCompatibilitySum(int[][] students, int[][] mentors) {
        int n = mentors.length;
        int[] dp = new int[1 << n];
        Arrays.fill(dp, Integer.MIN_VALUE);
        return dfs(0, students, mentors, dp, 0);
    }
    
    public int dfs(int index, int[][] s, int[][] m, int[] dp, int mask) {
        if (index == s.length) {
            return 0;
        }
        if (dp[mask] == Integer.MIN_VALUE) {
            for (int i = 0; i < m.length; i++) {
                if ((mask & (1 << i)) == 0) {
                    dp[mask] = Math.max(dp[mask], 
                                        count(s[index], m[i]) + dfs(index + 1, s, m, dp, mask + (1 << i)));
                }
            }
        }
        return dp[mask];
    }
    
    public int count(int[] nums1, int[] nums2) {
        int res = 0;
        for (int i = 0; i < nums1.length; i++) {
            if (nums1[i] == nums2[i]) {
                res++;
            }
        }
        return res;
    }
}
```

#### Relevant questions

* https://leetcode.com/problems/maximum-compatibility-score-sum/
* https://leetcode.com/problems/minimum-xor-sum-of-two-arrays/
* https://leetcode.com/problems/campus-bikes-ii/
