---
layout:     post
title:      LeetCode bit mask template
subtitle:   Bit mask in Java and relevant questions
date:       2021-07-30
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---

### Java Template
Use int bit operation to do memorization, for combination recursion.

- time = O(n!)
- space = O(n)

[Leetcode 1944. Number of Visible People in a Queue](https://leetcode.com/problems/number-of-visible-people-in-a-queue/)
```java
class Solution {
    public int[] canSeePersonsCount(int[] heights) {
        int[] res = new int[heights.length];
        Stack<Integer> stack = new Stack<>();
        for (int i = heights.length - 1; i >= 0; i--) {
            int count = 0;
            while (!stack.isEmpty() && heights[i] >= stack.peek()) {
                stack.pop();
                count++;
            }
            if (!stack.isEmpty()) {
                count++;
            }
            stack.push(heights[i]);
            res[i] = count;
        }
        return res;
    }
}
```

#### Relevant questions

* https://leetcode.com/problems/number-of-visible-people-in-a-queue/
* https://leetcode.com/problems/next-greater-element-ii/
* https://leetcode.com/problems/largest-rectangle-in-histogram/

