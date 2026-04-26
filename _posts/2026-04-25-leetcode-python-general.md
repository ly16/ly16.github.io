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
#### Sort

> list sort

```python
# in original list
a = [3, 1, 2]
a.sort()
print(a)  # [1, 2, 3]

# in new sorted list
a = [3, 1, 2]
b = sorted(a)
print(b)  # [1, 2, 3]
print(a)  # keep the same
```

> sort parameters

Using Timsort, which is a combination of insertion sort(small runs) and merge sort(merge sorted runs)
- time = best O(n), avg and worst O(nlogn)
- space = O(n)


```python
# descending sort
a.sort(reverse=True)

a = [(1, 3), (2, 1), (4, 2)]
a.sort(key=lambda x: x[1]) # by second variable
a = [(1, 3), (1, 2), (2, 1)]
a.sort(key=lambda x: (x[0], x[1])) # by sort first variable and then second variable
a.sort(key=lambda x: (x[0], -x[1]))
```
#### Binary Search

> Find the index of the first appearance (nums[index] <= target)

```python
import bisect

a = [1, 2, 4, 4, 5]
print(bisect.bisect_left(a, 4))  # 2
```


> Find the index of the first larger appearance ((nums[index] > target)

```python
import bisect

a = [1, 2, 4, 4, 5]
print(bisect.bisect_right(a, 4))  # 4
```
