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
|10|[Regular Expression Matching](https://github.com/ly16/LC-Practice/blob/master/Regular%20Expression%20Matching.java)|Hard| dp + dfs, similar to the wildcard, but * is only same as presending (DFS)|
|16|[3Sum Closest](https://github.com/ly16/LC-Practice/blob/master/3Sum%20Closest.java)|Medium|first theree numbers as inital sum (pointer)|
|17|[Letter Combinations of a Phone Number](https://github.com/ly16/LC-Practice/blob/master/Letter%20Combinations%20of%20a%20Phone%20Number.java)|Medium|use hashmap to store number and chars (DFS)|
|18|[4Sum](https://github.com/ly16/LC-Practice/blob/master/4%20Sum.java)|Medium|one addition + 3sum (pointer)|
|26|[Remove Duplicates from Sorted Array](https://github.com/ly16/LC-Practice/blob/master/Array%20Deduplication%20I.java)|Easy|(pointer)|
|28|[Implement strStr()](https://github.com/ly16/LC-Practice/blob/master/Determine%20If%20One%20String%20Is%20Another's%20Substring.java)|Easy|left the length of needle at the end (substr)|
|31|[Next Permutation](https://github.com/ly16/LC-Practice/blob/master/Next%20Permutation.java)|Medium|right side is descending order and reverse (pointer)|
|33|[ Search in Rotated Sorted Array](https://github.com/ly16/LC-Practice/blob/master/Search%20in%20Rotated%20Sorted%20Array.java)|Medium|two parts ascending (binary)|
|34|[Search for a Range](https://github.com/ly16/LC-Practice/blob/master/Search%20for%20a%20Range.java)|Medium|first occurence + last occurence (binary)|
|35|[Search Insert Position](https://github.com/ly16/LC-Practice/blob/master/Search%20Insert%20Position.java)|Easy|Last occurence, move the left first (binary)|
|39|[Combination Sum](https://github.com/ly16/LC-Practice/blob/master/Combination%20Sum.java)|Medium|repeatly use elements (DFS)|
|40|[Combination Sum II](https://github.com/ly16/LC-Practice/blob/master/Combination%20Sum%20II.java)|Medium|no duplicate like subset ii (DFS)|
|44|[Wildcard Matching](https://github.com/ly16/LC-Practice/blob/master/Wildcard%20Matching.java)|Hard|seperate star, question sign and DP record (DFS)|
|46|[Permutations](https://github.com/ly16/LC-Practice/blob/master/Permutations.java)|Medium|different from subset, i is from 0 not from start (DFS)|
|47|[Permutations II](https://github.com/ly16/LC-Practice/blob/master/Permutations%20II.java)|Medium|check the duplications, boolean array (DFS)|
|50|[Pow(x, n)](https://github.com/ly16/LC-Practice/blob/master/Pow(x%2C%20n).java)|Medium|x^n = x^(n/2) * x^(n/2) (binary)|
|51|[N-Queens](https://github.com/ly16/LC-Practice/blob/master/N%20Queens.java)|Hard|use Arraylist to record the col value and row index (DFS)|
|52|[N-Queens II](https://github.com/ly16/LC-Practice/blob/master/N-Queens%20II.java)|Hard|easier version of n-queen, only count distinct number (DFS)|
|57|[3Sum](https://github.com/ly16/LC-Practice/blob/master/3%20Sum.java)|Medium|(pointer)|
|60|[Permutation Sequence](https://github.com/ly16/LC-Practice/blob/master/Permutation%20Sequence.java)|Medium|find index k/factor and update k = k%factor (math)|
|69|[Sqrt(x)](https://github.com/ly16/LC-Practice/blob/master/Sqrt(x).java)|Easy|Last occurence, left move first (binary)|
|74|[Search a 2D Matrix](https://github.com/ly16/LC-Practice/blob/master/Search%20a%202D%20Matrix.java)|Medium|transfer from matrix into a array (binary)|
|75|[Sort Colors](https://github.com/ly16/LC-Practice/blob/master/Rainbow%20Sort.java)|Medium|three points, four blocks (pointer)|
|77|[Combinations](https://github.com/ly16/LC-Practice/blob/master/Combinations.java)|Medium|k is the size of each list (DFS)|
|78|[Subsets](https://github.com/ly16/LC-Practice/blob/master/All%20Subsets%20I.java)|Medium|add, dfs and remove (DFS)|
|79|[Word Search](https://github.com/ly16/LC-Practice/blob/master/Word%20Search.java)|Medium|i +/- 1 and j +/- 1 keep the order, i together and j together (DFS)|
|86|[Partition List](https://github.com/ly16/LC-Practice/blob/master/Partition%20Linked%20List.java)|Medium|two dummy heads, and concate (Linked List)|
|90|[Subsets II](https://github.com/ly16/LC-Practice/blob/master/All%20Subsets%20II.java)|Medium|for loop to keep each answer directly (DFS)|
|94|[Binary Tree Inorder Traversal](https://github.com/ly16/LC-Practice/blob/master/In-order%20Traversal%20Of%20Binary%20Tree.java)|Medium|if use iterative way, consider cur node and stack is empty (DFS)|
|98|[Validate Binary Search Tree](https://github.com/ly16/LC-Practice/blob/master/Validate%20Binary%20Search%20Tree.java)|Medium|long type (DFS)|
|100|[Same Tree](https://github.com/ly16/LC-Practice/blob/master/Symmetric%20Binary%20Tree.java)|Easy|every node should be same (DFS)|
|101|[Symmetric Tree](https://github.com/ly16/LC-Practice/blob/master/Symmetric%20Binary%20Tree.java)|Easy|symmtric by the root (DFS)|
|102|[Binary Tree Level Order Traversal](https://github.com/ly16/LC-Practice/blob/master/Get%20Keys%20In%20Binary%20Tree%20Layer%20By%20Layer.java)|Medium|BFS by level (BFS)|
|103|[Binary Tree Zigzag Level Order Traversal](https://github.com/ly16/LC-Practice/blob/master/Get%20Keys%20In%20Binary%20Tree%20Layer%20By%20Layer%20Zig-Zag%20Order.java)|Medium|traverse binary tree layer by layer different direction (BFS)|
|104|[Maximum Depth of Binary Tree](https://github.com/ly16/LC-Practice/blob/master/Maximum%20Depth%20of%20Binary%20Tree.java)|Easy|1+max(l,r) (DFS)|
|105|[Construct Binary Tree from Preorder and Inorder Traversal](https://github.com/ly16/LC-Practice/blob/master/Reconstruct%20Binary%20Tree%20With%20Preorder%20And%20Inorder.java)|Medium|find the root index in inorder (DFS)|
|106|[Construct Binary Tree from Inorder and Postorder Traversal](https://github.com/ly16/LC-Practice/blob/master/Construct%20Binary%20Tree%20from%20Inorder%20and%20Postorder%20Traversal.java)|Medium|find the root in inorder (DFS)|
|107|[Binary Tree Level Order Traversal II](https://github.com/ly16/LC-Practice/blob/master/Binary%20Tree%20Level%20Order%20Traversal%20II.java)|Easy|traverse layer by layer, reverse (BFS)|
|108|[Convert Sorted Array to Binary Search Tree](https://github.com/ly16/LC-Practice/blob/master/Convert%20Sorted%20Array%20to%20Binary%20Search%20Tree%20With%20Minimal%20Height.java)|Easy|two pointers (tree)|
|109|[Convert Sorted List to Binary Search Tree](https://github.com/ly16/LC-Practice/blob/master/Convert%20Sorted%20List%20to%20Binary%20Search%20Tree.java)|Medium|modifed find linked list middle (DFS)|
|110|[Balanced Binary Tree](https://github.com/ly16/LC-Practice/blob/master/Balanced%20Binary%20Tree.java)|Easy|from lower to higher -1 (DFS)|
|111|[Minimum Depth of Binary Tree](https://github.com/ly16/LC-Practice/blob/master/Minimum%20Depth%20of%20Binary%20Tree.java)|Easy|left+right+1, cannot be 0 (DFS)|
|112|[https://github.com/ly16/LC-Practice/blob/master/Path%20Sum.java](https://github.com/ly16/LC-Practice/blob/master/Path%20Sum.java)|Easy|reduced the current node.val (DFS)|
|114|[Flatten Binary Tree to Linked List](https://github.com/ly16/LC-Practice/blob/master/Flatten%20Binary%20Tree%20to%20Linked%20List.java)|Medium|record the right child first (DFS)|
|124|[Binary Tree Maximum Path Sum](https://github.com/ly16/LC-Practice/blob/master/Maximum%20Path%20Sum%20Binary%20Tree%20II.java)|Hard|return half and connect together (DFS)|
|125|[Valid Palindrome](https://github.com/ly16/LC-Practice/blob/master/Valid%20palindrome.java)|Easy|remove the invalid from two ends to the middle (substr)|
|126|[Word Ladder II](https://github.com/ly16/LC-Practice/blob/master/Word%20Ladder%20II.java)|Hard|hashmap has a set as value to store the words one step away from cur word (BFS+DFS)|
|127|[Word Ladder](https://github.com/ly16/LC-Practice/blob/master/Word%20Ladder.java)|Medium|change each char in the word to see in the dict, layer by layer (BFS)|
|130|[Surrounded Regions](https://github.com/ly16/LC-Practice/blob/master/Surrounded%20Regions.java)|Medium|up to down, left to right (BFS)|
|131|[Palindrome Partitioning](https://github.com/ly16/LC-Practice/blob/master/Palindrome%20Partitioning.java)|Medium|substring to partition (DFS)|
|133|[Clone Graph](https://github.com/ly16/LC-Practice/blob/master/Copy%20Graph.java)|Medium|bfs without layers (BFS)|
|139|[Word Break](https://github.com/ly16/LC-Practice/blob/master/Word%20Break.java)|Medium|true connect cut points (dp)|
|140|[Word Break II](https://github.com/ly16/LC-Practice/blob/master/Word%20Break%20II.java)|Hard|the order is reversed after dfs (DFS)|
|141|[Linked List Cycle](https://github.com/ly16/LC-Practice/blob/master/Check%20If%20Linked%20List%20Has%20A%20Cycle.java)|Easy|slow & fast pointer (linked list)|
|142|[Linked List Cycle II](https://github.com/ly16/LC-Practice/blob/master/Linked%20List%20Cycle%20II.java)|Medium|slow and fast pointer (linked list)|
|144|[Binary Tree Preorder Traversal](https://github.com/ly16/LC-Practice/blob/master/Binary%20Tree%20Preorder%20Traversal.java)|Medium|reverse the order, so right move in first for iterative method (DFS)|
|145|[Binary Tree Postorder Traversal](https://github.com/ly16/LC-Practice/blob/master/Binary%20Tree%20Postorder%20Traversal.java)|Hard|left, right, root from root, right, left (DFS)|
|146|[LRU Cache](https://github.com/ly16/LC-Practice/blob/master/Implement%20LRU%20Cache.java)|Hard|if existed, remove and append; not existed, node new or update and append (design)|
|148|[Sort List](https://github.com/ly16/LC-Practice/blob/master/Sort%20List.java)|Medium|merge sort and quick sort (sort)|
|153|[Find Minimum in Rotated Sorted Array](https://github.com/ly16/LC-Practice/blob/master/Find%20Minimum%20in%20Rotated%20Sorted%20Array.java)|Medium|smallest one is in the right ascending part (binary)|
|162|[Find Peak Element](https://github.com/ly16/LC-Practice/blob/master/Find%20Peak%20Element.java)|Medium|nums[mid] < nums[mid + 1] (binary)|
|167|[Two Sum II - Input array is sorted](https://github.com/ly16/LC-Practice/blob/master/2%20Sum%20II.java)|Easy|(pointer)|
|170|[Two Sum III - Data structure design](https://github.com/ly16/LC-Practice/blob/master/Two%20Sum%20III%20-%20Data%20structure%20design.java)|Easy|list can change length (hashMap)|
|173|[Binary Search Tree Iterator](https://github.com/ly16/LC-Practice/blob/master/Binary%20Search%20Tree%20Iterator.java)|Medium|find the smallest left first and then right, inorder (tree)|
|200|[Number of Islands](https://github.com/ly16/LC-Practice/blob/master/Number%20of%20Islands.java)|Medium|coordinate, change 1 to 0 after traverse (BFS)|
|205|[Isomorphic Strings](https://github.com/ly16/LC-Practice/blob/master/Isomorphic%20Strings.java)|Easy|match char to char by hashmap (hashmap)|
|207|[Course Schedule](https://github.com/ly16/LC-Practice/blob/master/Course%20Schedule.java)|Medium|topological sort, result size == numCourses (BFS)|
|208|[Implement Trie (Prefix Tree)](https://github.com/ly16/LC-Practice/blob/master/Implement%20Trie%20(Prefix%20Tree).java)|Medium|if end return true, use c-'a' to determine the index in the array (tree)|
|210|[Course Schedule II](https://github.com/ly16/LC-Practice/blob/master/Course%20Schedule%20II.java)|Medium|reverse the order of prerequisites (BFS)|
|212|[Word Search II](https://github.com/ly16/LC-Practice/blob/master/Word%20Search%20II.java)|Hard|use TrieNode, after find one word, put that end to null (DFS)|
|215|[Kth Largest Element in an Array](https://github.com/ly16/LC-Practice/blob/master/Kth%20Largest%20Element.java)|Medium|quick selection (sort)|
|216|[Combination Sum III](https://github.com/ly16/LC-Practice/blob/master/Combination%20Sum%20III.java)|Medium|only 1~9 are needed (DFS)|
|225|[Implement Stack using Queues](https://github.com/ly16/LC-Practice/blob/master/Implement%20Stack%20by%20Two%20Queues.java)|Easy|deliver all elements (except the last element) to another queue and then swap two queues (design)|
|230|[Kth Smallest Element in a BST](https://github.com/ly16/LC-Practice/blob/master/Kth%20Smallest%20Element%20in%20a%20BST.java)|Medium|inorder traverse (DFS)|
|232|[Implement Queue using Stacks](https://github.com/ly16/LC-Practice/blob/master/Implement%20Queue%20using%20Stacks.java)|Easy|one stack is for storage, and another stack is for poll out (design)|
|235|[Lowest Common Ancestor of a Binary Search Tree](https://github.com/ly16/LC-Practice/blob/master/Lowest%20Common%20Ancestor%20I.java)|Easy|both not null return root (DFS)|
|236|[Lowest Common Ancestor of a Binary Tree](https://github.com/ly16/LC-Practice/blob/master/Lowest%20Common%20Ancestor%20I.java)|Medium|not sure existed (DFS)|
|240|[Search a 2D Matrix II](https://github.com/ly16/LC-Practice/blob/master/Search%20a%202D%20Matrix%20II.java)|Medium|from the lower left (pointer)|
|257|[Binary Tree Paths](https://github.com/ly16/LC-Practice/blob/master/Binary%20Tree%20Paths.java)|Easy|a new string each level (DFS)|
|259|[3Sum Smaller](https://github.com/ly16/LC-Practice/blob/master/3Sum%20Smaller.java)|Medium|Don't move right, but count the interval of left and right (pointer)|
|261|[Graph Valid Tree](https://github.com/ly16/LC-Practice/blob/master/Graph%20Valid%20Tree.java)|Medium|construct graph and bfs (BFS)|
|263|[Ugly Number](https://github.com/ly16/LC-Practice/blob/master/Ugly%20Number.%20java)|Easy|devided by 2,3,5 repeatedly (math)|
|264|[Ugly Number II](https://github.com/ly16/LC-Practice/blob/master/Ugly%20Number%20II.java)|Medium|index times factor and compare each possible products (dp)|
|266|[Palindrome Permutation](https://github.com/ly16/LC-Practice/blob/master/Palindrome%20Permutation.java)|Easy|there should be no additional or only 1 additional char (hash table)|
|267|[Palindrome Permutation II](https://github.com/ly16/LC-Practice/blob/master/Palindrome%20Permutation%20II.java)|Medium|half even number permutations, symmetric (DFS)|
|269|[ Alien Dictionary](https://github.com/ly16/LC-Practice/blob/master/Alien%20Dictionary.java)|Hard|construct the map (BFS)|
|270|[Closest Binary Search Tree Value](https://github.com/ly16/LC-Practice/blob/master/Closest%20Number%20In%20Binary%20Search%20Tree.java)|Easy|the property of BST (tree)|
|272|[Closest Binary Search Tree Value II](https://github.com/ly16/LC-Practice/blob/master/Closest%20Binary%20Search%20Tree%20Value%20II.java)|Hard|two stack, two pointers (tree)|
|278|[First Bad Version](https://github.com/ly16/LC-Practice/blob/master/First%20Bad%20Version.java)|Easy|first occurance, move the right first (binary)|
|283|[Move Zeroes](https://github.com/ly16/LC-Practice/blob/master/Move%200s%20To%20The%20End%20II.java)|Easy|slow records ans (pointer)|
|285|[Inorder Successor in BST](https://github.com/ly16/LC-Practice/blob/master/Inorder%20Successor%20in%20BST.java)|Medium|find the target and than to the right child and left first (tree)|
|290|[Word Pattern](https://github.com/ly16/LC-Practice/blob/master/Word%20Pattern.java)|Easy|match char and string (hashmap)|
|291|[Word Pattern II](https://github.com/ly16/LC-Practice/blob/master/Word%20Pattern%20II.java)|Hard|DFS is boolean and use map and set to match char and string (DFS)|
|297|[Serialize and Deserialize Binary Tree](https://github.com/ly16/LC-Practice/blob/master/Binary%20Tree%20Serialization.java)|Hard|print binary tree layer by layer (BFS)|
|300|[Longest Increasing Subsequence](https://github.com/ly16/LC-Practice/blob/master/Longest%20Ascending%20Subsequence.java)|Medium|First occurence (binary)|
|301|[Remove Invalid Parentheses](https://github.com/ly16/LC-Practice/blob/master/Remove%20Invalid%20Parentheses.java)|Hard| substring to remove the current char (DFS)|
|346|[Moving Average from Data Stream](https://github.com/ly16/LC-Practice/blob/master/Moving%20Average%20from%20Data%20Stream.java)|Easy|sliding window by the queue (design)|
|380|[Insert Delete GetRandom O(1)](https://github.com/ly16/LC-Practice/blob/master/Insert%20Delete%20GetRandom%20O(1).java)|Medium|import java.util.Random, arrayList swap with the last item and delete (design)|
|381|[Insert Delete GetRandom O(1) - Duplicates allowed](https://github.com/ly16/LC-Practice/blob/master/Insert%20Delete%20GetRandom%20O(1)%20-%20Duplicates%20allowed.java)|Hard|copy the last element to replace the target, and remove the last item; also update the position in the map (design)|
|387|[First Unique Character in a String](https://github.com/ly16/LC-Practice/blob/master/First%20Unique%20Character%20in%20a%20String.java)|Easy|use int[256] to record time of occurance (hashtable)|
|409|[Longest Palindrome](https://github.com/ly16/LC-Practice/blob/master/Longest%20Palindrome.java)|Easy|The longest could be odd, so even + 1 (substr)|
|450|[Delete Node in a BST](https://github.com/ly16/LC-Practice/blob/master/Delete%20Node%20in%20a%20BST.java)|Medium|find the smallest on right child (DFS)|
|516|[Longest Palindromic Subsequence](https://github.com/ly16/LC-Practice/blob/master/Longest%20Palindromic%20Subsequence.java)|Medium|2d-dp as #5 (substr)|
|653|[Two Sum IV - Input is a BST](https://github.com/ly16/LC-Practice/blob/master/Two%20Sum%20IV%20-%20Input%20is%20a%20BST.java)|Easy|same as two sum (pointer)|
|658|[Find K Closest Elements](https://github.com/ly16/LC-Practice/blob/master/K%20Closest%20In%20Sorted%20Array.java)|Medium|last occurence (binary)|
|680|[Valid Palindrome II](https://github.com/ly16/LC-Practice/blob/master/Valid%20Palindrome%20II.java)|Easy|(pointer)|
|681|[Next Closest Time](https://github.com/ly16/LC-Practice/blob/master/Next%20Closest%20Time.java)|Medium|convert to miniute from integer (DFS)|

______________________________________________

###### Last Update: 06/10/2018
