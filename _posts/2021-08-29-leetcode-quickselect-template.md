---
layout:     post
title:      LeetCode quick sort/select template
subtitle:   quick sort / select in Java and relevant questions
date:       2021-08-29
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode
---

### quick sort Java template

```java
public class QuickSort {
    public static void quickSort(int[] nums) {
        if (nums == null || nums.length == 0) {
            return;
        }
        sort(nums, 0, nums.length - 1);
    }

    public static void sort(int[] nums, int start, int end) {
        if (start >= end) {
            return;
        }

        int left = start;
        int right = end;
        int pivot = nums[left + (right - left) / 2];

        while (left <= right) {
            while (left <= right && nums[left] < pivot) {
                left++;
            }
            while (left <= right && nums[right] > pivot) {
                right--;
            }

            if (left <= right) {
                swap(nums, left++, right--);
            }
        }
        sort(nums, start, right);
        sort(nums, left, end);
    }

    public static void swap(int[] nums, int left, int right) {
        int tmp = nums[left];
        nums[left] = nums[right];
        nums[right] = tmp;
    }
}
```

### quick select java template

```java
public class QuickSelect {
    public int findKthLargest(int[] nums, int k) {
        return quickSelect(nums, 0, nums.length - 1, k);
    }
    public int quickSelect(int[] nums, int start, int end, int k) {
        int left = start;
        int right = end;
        int pivot = nums[(left + right) / 2];
        while(left <= right) {
            // sort from large to small, so the left part is larger
            // similar as find the kth the smallest one
            while (left <= right && nums[left] > pivot) {
                left++;
            }
            while (left <= right && nums[right] < pivot) {
                right--;
            }

            if (left <= right) {
                swap(nums,left++, right--);
            }
        }

        if (start + k - 1 <= right) {
            return quickSelect(nums, start, right, k);
        }
        if (start + k - 1 >= left) {
            return quickSelect(nums,  left, end, k - (left - start));
        }
        return nums[right + 1];
    }

    public void swap(int[] nums, int left, int right) {
        int tmp = nums[left];
        nums[left] = nums[right];
        nums[right] = tmp;
    }
}
```


#### Relevant questions & reference

* https://leetcode.com/problems/kth-largest-element-in-an-array/
* https://leetcode.com/problems/top-k-frequent-elements/
* https://leetcode.com/problems/k-closest-points-to-origin/
