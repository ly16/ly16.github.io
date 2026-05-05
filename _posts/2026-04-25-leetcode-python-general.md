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

#### Data Structure
> imports pkg
```python
from typing import List, Dict, Set, Tuple, Counter, Optional
from collections import deque, defaultdict, Counter
import bisect
import math
import heapq
```

> dict

| Concept      | Java (`HashMap`)                            | Python (`dict`) |
| ------------ | ------------------------------------------- | --------------- |
| Create       | `Map<String, Integer> m = new HashMap<>();` | `d = {}`, `d = defaultdict(int)`|
| Put          | `m.put("a", 1);`                            | `d["a"] = 1` , `d['apple'] += 1 `|
| Get          | `m.get("a")`                                | `d["a"]`        |
| Get default  | `m.getOrDefault("a", 0)`                    | `d.get("a", 0)` |
| Contains key | `m.containsKey("a")`                        | `"a" in d`      |
| Remove       | `m.remove("a")`                             | `d.pop("a")`    |
| Size         | `m.size()`                                  | `len(d)`        |
| computeIfAbsent | `m.computeIfAbsent(k, key -> new ArrayList<>()).add(v)` | `d.setdefault(k, []).append(v)`|

> deque
```python
from collections import deque

# initialization
d = deque()
d = deque([1, 2, 3])      # From a list
d = deque("abc")          # From a string: deque(['a', 'b', 'c'])

d.append(x)
d.pop()
d.appendleft(x)
d.popleft()

```

#### Array

| Category | Operation & Syntax | Behavior | Time Complexity |
| :--- | :--- | :--- | :--- |
| **Adding** | `list.append(x)` | Appends elements to the end. | $O(1)$ amortized |
| | `list.insert(i, x)` | Squeezes `x` in at index `i`, shifting existing items. | $O(N)$ |
| | `list.extend(iterable)` | Appends all items from an iterable. | $O(K)$ |
| **Replacing** | `list[i] = x` | Overwrites index `i` in-place. Size does not change. | $O(1)$ |
| **Removing** | `list.pop([i])` | Removes and returns item at index (default: last). | $O(1)$ end / $O(N)$ elsewhere |
| | `list.remove(x)` | Deletes first occurrence of value `x`. | $O(N)$ |
| | `del list[i:j]` | Deletes an entire index range/slice in-place. | $O(N)$ |

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
