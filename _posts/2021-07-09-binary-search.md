---
layout:     post
title:      LeetCode binary search template
subtitle:   classic binary search, left/right boundary
date:       2021-07-09
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---

### Binary search Template


##### Classic Binary Search

```java
public static int binarySearch(int[] array, int target) {
	int left = 0, right = array.length - 1;
	while (left <= right) {
		int mid = left + (right - left) / 2;
		if (array[mid] == target) {
			return mid;
		} else if (array[mid] > target) {
			right = mid - 1;
		} else {
			left = mid + 1;
		}
	}
	return -1;
}
```

##### Left/Right boundary

```java
	
public static int leftBound(int[] array, int target) {
	int left = 0, right = array.length - 1;
	while (left < right) {
		int mid = left + (right - left) / 2;
		if (array[mid] < target) {
			left = mid + 1;
		} else {
			right = mid;
		}
	}
	return array[right] == target ? right : -1;
}
	
public static int rightBound(int[] array, int target) {
	int left = 0, right = array.length - 1;
	while (left + 1 < right) {
		int mid = left + (right - left) / 2;
		if (array[mid] > target) {
			right = mid - 1;
		} else {
			left = mid;
		}
	}
	if (array[right] == target) {
		return right;
	}
	if (array[left] == target) {
		return left;
	}
	return -1;
}
 
```

##### Similar questions

- https://leetcode.com/problems/capacity-to-ship-packages-within-d-days/
- https://leetcode.com/problems/koko-eating-bananas/
- https://leetcode.com/problems/find-the-smallest-divisor-given-a-threshold/
- https://leetcode.com/problems/sum-of-mutated-array-closest-to-target/
