---
layout:     post
title:      LeetCode Record Summary
subtitle:   first 300 round one
date:       2018-05-18
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---

### Record of Submissions

|    #    | Name & Solution |Difficulty|Hint|
| ---------- | --- |---|---|
|1|[Two Sum](https://github.com/ly16/LC-Practice/blob/master/2%20Sum.java)|Easy|(hashMap)|
|3|[Longest Substring Without Repeating Characters](https://github.com/ly16/LC-Practice/blob/master/Longest%20Substring%20Without%20Repeating%20Characters.java)|Medium|slow and fast, to the new position (pointer)|
|5|[Longest Palindromic Substring](https://github.com/ly16/LC-Practice/blob/master/Longest%20Palindromic%20Substring.java)|Medium|Even or odd length (substr)|
|16|[3Sum Closest](https://github.com/ly16/LC-Practice/blob/master/3Sum%20Closest.java)|Medium|first theree numbers as inital sum (pointer)|
|18|[4Sum](https://github.com/ly16/LC-Practice/blob/master/4%20Sum.java)|Medium|one addition + 3sum (pointer)|
|26|[Remove Duplicates from Sorted Array](https://github.com/ly16/LC-Practice/blob/master/Array%20Deduplication%20I.java)|Easy|(pointer)|
|28|[Implement strStr()](https://github.com/ly16/LC-Practice/blob/master/Determine%20If%20One%20String%20Is%20Another's%20Substring.java)|Easy|left the length of needle at the end (substr)|
|33|[ Search in Rotated Sorted Array](https://github.com/ly16/LC-Practice/blob/master/Search%20in%20Rotated%20Sorted%20Array.java)|Medium|two parts ascending (binary)|
|34|[Search for a Range](https://github.com/ly16/LC-Practice/blob/master/Search%20for%20a%20Range.java)|Medium|first occurence + last occurence (binary)|
|35|[Search Insert Position](https://github.com/ly16/LC-Practice/blob/master/Search%20Insert%20Position.java)|Easy|Last occurence, move the left first (binary)|
|50|[Pow(x, n)](https://github.com/ly16/LC-Practice/blob/master/Pow(x%2C%20n).java)|Medium|x^n = x^(n/2) * x^(n/2) (binary)|
|57|[3Sum](https://github.com/ly16/LC-Practice/blob/master/3%20Sum.java)|Medium|(pointer)|
|69|[Sqrt(x)](https://github.com/ly16/LC-Practice/blob/master/Sqrt(x).java)|Easy|Last occurence, left move first (binary)|
|74|[Search a 2D Matrix](https://github.com/ly16/LC-Practice/blob/master/Search%20a%202D%20Matrix.java)|Medium|transfer from matrix into a array (binary)|
|75|[Sort Colors](https://github.com/ly16/LC-Practice/blob/master/Rainbow%20Sort.java)|Medium|three points, four blocks (pointer)|
|86|[Partition List](https://github.com/ly16/LC-Practice/blob/master/Partition%20Linked%20List.java)|Medium|two dummy heads, and concate (Linked List)|
|94|[Binary Tree Inorder Traversal](https://github.com/ly16/LC-Practice/blob/master/In-order%20Traversal%20Of%20Binary%20Tree.java)|Medium|if use iterative way, consider cur node and stack is empty (DFS)|
|98|[Validate Binary Search Tree](https://github.com/ly16/LC-Practice/blob/master/Validate%20Binary%20Search%20Tree.java)|Medium|long type (DFS)|
|100|[Same Tree](https://github.com/ly16/LC-Practice/blob/master/Symmetric%20Binary%20Tree.java)|Easy|every node should be same (DFS)|
|101|[Symmetric Tree](https://github.com/ly16/LC-Practice/blob/master/Symmetric%20Binary%20Tree.java)|Easy|symmtric by the root (DFS)|
|102|[Binary Tree Level Order Traversal](https://github.com/ly16/LC-Practice/blob/master/Get%20Keys%20In%20Binary%20Tree%20Layer%20By%20Layer.java)|Medium|BFS by level (BFS)|
|103|[Binary Tree Zigzag Level Order Traversal](https://github.com/ly16/LC-Practice/blob/master/Get%20Keys%20In%20Binary%20Tree%20Layer%20By%20Layer%20Zig-Zag%20Order.java)|Medium|traverse binary tree layer by layer different direction (BFS)|
|104|[Maximum Depth of Binary Tree](https://github.com/ly16/LC-Practice/blob/master/Maximum%20Depth%20of%20Binary%20Tree.java)|Easy|1+max(l,r) (DFS)|
|107|[Binary Tree Level Order Traversal II](https://github.com/ly16/LC-Practice/blob/master/Binary%20Tree%20Level%20Order%20Traversal%20II.java)|Easy|traverse layer by layer, reverse (BFS)|
|110|[Balanced Binary Tree](https://github.com/ly16/LC-Practice/blob/master/Balanced%20Binary%20Tree.java)|Easy|from lower to higher -1 (DFS)|
|111|[Minimum Depth of Binary Tree](https://github.com/ly16/LC-Practice/blob/master/Minimum%20Depth%20of%20Binary%20Tree.java)|Easy|left+right+1, cannot be 0 (DFS)|
|114|[Flatten Binary Tree to Linked List](https://github.com/ly16/LC-Practice/blob/master/Flatten%20Binary%20Tree%20to%20Linked%20List.java)|Medium|record the right child first (DFS)|
|125|[Valid Palindrome](https://github.com/ly16/LC-Practice/blob/master/Valid%20palindrome.java)|Easy|remove the invalid from two ends to the middle (substr)|
|127|[Word Ladder](https://github.com/ly16/LC-Practice/blob/master/Word%20Ladder.java)|Medium|change each char in the word to see in the dict, layer by layer (BFS)|
|130|[Surrounded Regions](https://github.com/ly16/LC-Practice/blob/master/Surrounded%20Regions.java)|Medium|up to down, left to right (BFS)|
|133|[Clone Graph](https://github.com/ly16/LC-Practice/blob/master/Copy%20Graph.java)|Medium|bfs without layers (BFS)|
|141|[Linked List Cycle](https://github.com/ly16/LC-Practice/blob/master/Check%20If%20Linked%20List%20Has%20A%20Cycle.java)|Easy|slow & fast pointer (linked list)|
|142|[Linked List Cycle II](https://github.com/ly16/LC-Practice/blob/master/Linked%20List%20Cycle%20II.java)|Medium|slow and fast pointer (linked list)|
|144|[Binary Tree Preorder Traversal](https://github.com/ly16/LC-Practice/blob/master/Binary%20Tree%20Preorder%20Traversal.java)|Medium|reverse the order, so right move in first for iterative method (DFS)|
|145|[Binary Tree Postorder Traversal](https://github.com/ly16/LC-Practice/blob/master/Binary%20Tree%20Postorder%20Traversal.java)|Hard|left, right, root from root, right, left (DFS)|
|148|[Sort List](https://github.com/ly16/LC-Practice/blob/master/Sort%20List.java)|Medium|merge sort and quick sort (sort)|
|153|[Find Minimum in Rotated Sorted Array](https://github.com/ly16/LC-Practice/blob/master/Find%20Minimum%20in%20Rotated%20Sorted%20Array.java)|Medium|smallest one is in the right ascending part (binary)|
|162|[Find Peak Element](https://github.com/ly16/LC-Practice/blob/master/Find%20Peak%20Element.java)|Medium|nums[mid] < nums[mid + 1] (binary)|
|167|[Two Sum II - Input array is sorted](https://github.com/ly16/LC-Practice/blob/master/2%20Sum%20II.java)|Easy|(pointer)|
|170|[Two Sum III - Data structure design](https://github.com/ly16/LC-Practice/blob/master/Two%20Sum%20III%20-%20Data%20structure%20design.java)|Easy|list can change length (hashMap)|
|173|[Binary Search Tree Iterator](https://github.com/ly16/LC-Practice/blob/master/Binary%20Search%20Tree%20Iterator.java)|Medium|find the smallest left first and then right, inorder (tree)|
|200|[Number of Islands](https://github.com/ly16/LC-Practice/blob/master/Number%20of%20Islands.java)|Medium|coordinate, change 1 to 0 after traverse (BFS)|
|207|[Course Schedule](https://github.com/ly16/LC-Practice/blob/master/Course%20Schedule.java)|Medium|topological sort, result size == numCourses (BFS)|
|210|[Course Schedule II](https://github.com/ly16/LC-Practice/blob/master/Course%20Schedule%20II.java)|Medium|reverse the order of prerequisites (BFS)|
|215|[Kth Largest Element in an Array](https://github.com/ly16/LC-Practice/blob/master/Kth%20Largest%20Element.java)|Medium|quick selection (sort)|
|230|[Kth Smallest Element in a BST](https://github.com/ly16/LC-Practice/blob/master/Kth%20Smallest%20Element%20in%20a%20BST.java)|Medium|inorder traverse (DFS)|
|240|[Search a 2D Matrix II](https://github.com/ly16/LC-Practice/blob/master/Search%20a%202D%20Matrix%20II.java)|Medium|from the lower left (pointer)|
|259|[3Sum Smaller](https://github.com/ly16/LC-Practice/blob/master/3Sum%20Smaller.java)|Medium|Don't move right, but count the interval of left and right (pointer)|
|261|[Graph Valid Tree](https://github.com/ly16/LC-Practice/blob/master/Graph%20Valid%20Tree.java)|Medium|construct graph and bfs (BFS)|
|269|[ Alien Dictionary](https://github.com/ly16/LC-Practice/blob/master/Alien%20Dictionary.java)|Hard|construct the map (BFS)|
|270|[Closest Binary Search Tree Value](https://github.com/ly16/LC-Practice/blob/master/Closest%20Number%20In%20Binary%20Search%20Tree.java)|Easy|the property of BST (tree)|
|272|[Closest Binary Search Tree Value II](https://github.com/ly16/LC-Practice/blob/master/Closest%20Binary%20Search%20Tree%20Value%20II.java)|Hard|two stack, two pointers (tree)|
|278|[First Bad Version](https://github.com/ly16/LC-Practice/blob/master/First%20Bad%20Version.java)|Easy|first occurance, move the right first (binary)|
|283|[Move Zeroes](https://github.com/ly16/LC-Practice/blob/master/Move%200s%20To%20The%20End%20II.java)|Easy|slow records ans (pointer)|
|285|[Inorder Successor in BST](https://github.com/ly16/LC-Practice/blob/master/Inorder%20Successor%20in%20BST.java)|Medium|find the target and than to the right child and left first (tree)|
|297|[Serialize and Deserialize Binary Tree](https://github.com/ly16/LC-Practice/blob/master/Binary%20Tree%20Serialization.java)|Hard|print binary tree layer by layer (BFS)|
|300|[Longest Increasing Subsequence](https://github.com/ly16/LC-Practice/blob/master/Longest%20Ascending%20Subsequence.java)|Medium|First occurence (binary)|
|409|[Longest Palindrome](https://github.com/ly16/LC-Practice/blob/master/Longest%20Palindrome.java)|Easy|The longest could be odd, so even + 1 (substr)|
|516|[Longest Palindromic Subsequence](https://github.com/ly16/LC-Practice/blob/master/Longest%20Palindromic%20Subsequence.java)|Medium|2d-dp as #5 (substr)|
|653|[Two Sum IV - Input is a BST](https://github.com/ly16/LC-Practice/blob/master/Two%20Sum%20IV%20-%20Input%20is%20a%20BST.java)|Easy|same as two sum (pointer)|
|658|[Find K Closest Elements](https://github.com/ly16/LC-Practice/blob/master/K%20Closest%20In%20Sorted%20Array.java)|Medium|last occurence (binary)|
|680|[Valid Palindrome II](https://github.com/ly16/LC-Practice/blob/master/Valid%20Palindrome%20II.java)|Easy|(pointer)|


______________________________________________

###### Last Update: 05/28/2018
