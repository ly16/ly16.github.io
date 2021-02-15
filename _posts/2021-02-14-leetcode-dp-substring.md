---
layout:     post
title:      LeetCode dp template -- substring
subtitle:   dp and substring type in Java and relevant questions
date:       2021-02-14
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---

### Palindrome dp Template


##### Longest Palindromic Substring
- time = O(n^2) 
- space = O(n^2)


```java
class Solution {
    public String longestPalindrome(String s) {
        if (s == null || s.length() == 0) {
            return "";
        }
        int n = s.length();
        boolean[][] dp = new boolean[n][n];
        int max = 0;
        int start = 0;
        for (int i = s.length() - 1; i >= 0; i--) {
            for (int j = i; j < s.length(); j++) {
                if (s.charAt(i) == s.charAt(j)) {
                    if (i == j || j - i == 1 || dp[i + 1][j - 1]) {
                        dp[i][j] = true;
                        if (j - i + 1 > max) {
                            max = j - i + 1;
                            start = i;
                        }
                    }
                }
            }
        }
       
        return s.substring(start, start + max);
    }
}
```

Similar Questions:

* https://leetcode.com/problems/longest-palindromic-subsequence/
* https://leetcode.com/problems/palindromic-substrings/
* https://leetcode.com/problems/longest-common-subsequence/
* https://leetcode.com/problems/longest-palindromic-substring/



##### Longest Common Subsequence (LCS)

- time = O(mn)
- space = O(mn)

```java
class Solution {
    public int longestCommonSubsequence(String text1, String text2) {
        int m = text1.length();
        int n = text2.length();
        int[][] dp  = new int[m + 1][n + 1];
        
        for (int i  = 0; i <= m; i++) {
            for (int j = 0; j <= n; j++) {
                if (i == 0 || j == 0) {
                    dp[i][j] = 0;
                    continue;
                } 
                if (text1.charAt(i - 1) ==  text2.charAt(j - 1)) {
                    dp[i][j] = 1 + dp[i - 1][j - 1];
                } else {
                    dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]);
                }
            }
        }
        return dp[m][n];
    }
}
```

Similar questions:

* https://leetcode.com/problems/edit-distance/
* https://leetcode.com/problems/delete-operation-for-two-strings/
* https://leetcode.com/problems/longest-common-subsequence/
* https://leetcode.com/problems/minimum-ascii-delete-sum-for-two-strings/


#####  Longest Increasing Subsequence (LIS)

dp version

- time = O(n^2)
- space = O(n)

```java
class Solution {
    public int lengthOfLIS(int[] nums) {
        if (nums == null || nums.length == 0) {
            return 0;
        }
        int[] dp = new int[nums.length];
        dp[0] = 1;
        int max = 1;
        for (int i = 1; i < nums.length; i++) {
            int localMax = 0;
            for (int j = 0; j < i; j++) {
                if (nums[j] < nums[i]) {
                    localMax = Math.max(localMax, dp[j]);
                }
            }
            dp[i] = localMax + 1;
            max = Math.max(max, dp[i]);
        }
        return max;
    }
}
```

> dp + binary version (optimization)

- time = O(nlogn)
- space = O(n)

```java
public class Solution {
    public int lengthOfLIS(int[] nums) {
        int[] dp = new int[nums.length];
        int len = 0;
        for (int num : nums) {
            int i = Arrays.binarySearch(dp, 0, len, num);
            if (i < 0) {
                i = -(i + 1);
            }
            dp[i] = num;
            if (i == len) {
                len++;
            }
        }
        return len;
    }
}
```

Similar questions

* https://leetcode.com/problems/russian-doll-envelopes/
* https://leetcode.com/problems/longest-increasing-subsequence/
* https://leetcode.com/problems/number-of-longest-increasing-subsequence/

