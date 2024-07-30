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
class Solution {
    public int[] sortArray(int[] nums) {
        if (nums == null || nums.length <= 1) {
            return nums;
        }
        quickSort(nums, 0, nums.length - 1);
        return nums;
    }

    public void quickSort(int[] nums, int start, int end) {
        if (start >= end) {
            return;
        }
        int pivot = partition(nums, start, end);
        quickSort(nums, start, pivot - 1);
        quickSort(nums, pivot + 1, end);
    }

    public int partition(int[] nums, int start, int end) {
        if (start == end) {
            return start;
        }
        int pivot = nums[end];
        int slow = start;
        for (int fast = start; fast < end; fast++) {
            if (nums[fast] <= pivot) {
                swap(nums, slow++, fast); 
            }
        }
        swap(nums, slow, end);
        return slow;
    }

    public void swap(int[] nums, int left, int right) {
        int temp = nums[left];
        nums[left] = nums[right];
        nums[right] = temp;
    }
}
```

### quick select java template
#### with additional arrays

```java
class Solution {
     public int findKthLargest(int[] nums, int k) {
        List<Integer> list = new ArrayList<>();
        for (int num: nums) {
            list.add(num);
        }
        
        return quickSelect(list, k);
    }
    
    public int quickSelect(List<Integer> nums, int k) {
        int pivotIndex = new Random().nextInt(nums.size());
        int pivot = nums.get(pivotIndex);

        List<Integer> left = new ArrayList<>();
        List<Integer> mid = new ArrayList<>();
        List<Integer> right = new ArrayList<>();

        for (int num : nums) {
            if (num > pivot) { // left hand is the larger part
                left.add(num);
            } else if (num < pivot) {
                right.add(num);
            } else {
                mid.add(num);
            }
        }
        
        if (left.size() >= k) {
            return quickSelect(left, k);
        }
 
        if (left.size() + mid.size() < k) {
            return quickSelect(right, k - left.size() - mid.size());
        }
        return pivot;
    }
}
```

#### without additional arrays

```java
class Solution {
    public int findKthLargest(int[] nums, int k) {
        if (nums == null || nums.length < k) {
            return -1;
        }
        return quickSelect(nums, 0, nums.length - 1, k);
    }

    public int quickSelect(int[] nums, int start, int end, int k) {
        int partition = dfs(nums, start, end); 
        if (partition == k - 1) {
            return nums[partition];
        }
        if (partition > k - 1) {
            return quickSelect(nums, start, partition - 1, k);
        }
        return quickSelect(nums, partition + 1, end, k);
    }

    public int dfs(int[] nums, int start, int end) {
        int pivotIndex = new Random().nextInt(end - start + 1) + start;
        int pivot = nums[pivotIndex];
        swap(nums, pivotIndex, end); 
        int slow = start;
        for (int i = start; i < end; i++) {
            if (nums[i] >= pivot) { // left hand is the larger part
                swap(nums, slow++, i);
            }
        }
        swap(nums, slow, end);
        return slow;
    }

    public void swap(int[] nums, int left, int right) {
        int temp = nums[left];
        nums[left] = nums[right];
        nums[right] = temp;
    }
}
```



#### Relevant questions & reference

* https://leetcode.com/problems/kth-largest-element-in-an-array/
* https://leetcode.com/problems/top-k-frequent-elements/
* https://leetcode.com/problems/k-closest-points-to-origin/
