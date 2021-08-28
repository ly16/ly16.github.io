---
layout:     post
title:      LeetCode manache template
subtitle:   Using manache for palindrome in Java and relevant questions
date:       2021-08-27
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---

### Java Template
Manache algo to find longest palindrome
1. original for odd number palindrome
2. we can build odd/even number string to odd number by adding '#' between each char
e.g aba -> a#b#a, aa -> a#a

- time = O(n)
- space = O(n)

[5. Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring/)
```java
class Solution {
    public String longestPalindrome(String s) {
        StringBuilder sb = new StringBuilder();
        sb.append("#");
        for (char c : s.toCharArray()) {
            sb.append(c);
            sb.append("#");
        }
        String t = sb.toString();
        
        int[] memo = new int[t.length()];
        int maxRight = 0, maxCenter = -1;
        for (int i = 0; i < t.length(); i++) {
            int curRadius = 0;
            if (i < maxRight) {
                int j = 2 * maxCenter - i;
                curRadius = Math.min(memo[j], maxRight - i);
                while (i + curRadius < t.length() && i - curRadius >= 0 
                       && t.charAt(i + curRadius) == t.charAt(i - curRadius)) {
                    curRadius++;
                }
            } else {
                while (i + curRadius < t.length() && i - curRadius >= 0 
                       && t.charAt(i + curRadius) == t.charAt(i - curRadius)) {
                    curRadius++;
                }
            }
            if (curRadius - 1 + i > maxRight) {
                maxRight = curRadius - 1 + i;
                maxCenter = i;
            }
            memo[i] = curRadius - 1;
        }
        int maxRadius = 0;
        for (int i = 0; i < memo.length; i++) {
            if (memo[i] > maxRadius) {
                maxRadius = memo[i];
                maxCenter = i;
            }
        }
        
        return s.substring(maxCenter/2 - maxRadius/2, maxCenter/2 + (maxRadius + 1) /2);
    }
}
```

#### Relevant questions

* https://leetcode.com/problems/longest-palindromic-substring/
* https://leetcode.com/problems/palindromic-substrings/
* https://leetcode.com/problems/maximum-product-of-the-length-of-two-palindromic-substrings/
