---
layout:     post
title:      LeetCode Python template
subtitle:   Basic API for Python algorithm
date:       2026-04-25
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---

#### Array
#### String
#### Binary Search

1. Find the index of the first appearance (nums[index] <= target)
```python
import bisect

a = [1, 2, 4, 4, 5]
print(bisect.bisect_left(a, 4))  # 2
```

2. Find the index of the first larger appearance ((nums[index] > target)

```python
import bisect

a = [1, 2, 4, 4, 5]
print(bisect.bisect_right(a, 4))  # 4
```
