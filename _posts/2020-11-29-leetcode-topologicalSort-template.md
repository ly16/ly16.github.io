---
layout:     post
title:      LeetCode Topological Sort template
subtitle:   Topological Sort in Java and relevant questions
date:       2020-12-29
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---

### Java Template
Use priority Queue for BFS graph traversal

- time = O((E+V)logV) = O(ElogV)
- space = O(V)

[207. Course Schedule](https://leetcode.com/problems/course-schedule/)

```java
class Solution {
    public boolean canFinish(int numCourses, int[][] prerequisites) {
        if (prerequisites == null || prerequisites.length == 0
           || prerequisites[0] == null || prerequisites[0].length == 0) {
            return true;
        }
        // indegree map
        Map<Integer, Integer> indegree = new HashMap<>();
        // neighbor map
        // consider some course has no prerequisites also belongs to head
        Map<Integer, List<Integer>> neighbors = new HashMap<>();
        for (int i = 0; i < numCourses; i++) {
            indegree.put(i, 0);
        }
        // update the indegree and neighbor map
        for (int[] pair : prerequisites) {
            indegree.put(pair[0], indegree.get(pair[0]) + 1);
            if (!neighbors.containsKey(pair[1])) {
                neighbors.put(pair[1], new ArrayList<Integer>());
            }
            neighbors.get(pair[1]).add(pair[0]);
        }
        // find the head of 0 in-degree
        int count = 0;
        Queue<Integer> queue = new LinkedList<>();
        for (int i = 0; i < numCourses; i++) {
            if (indegree.get(i) == 0) {
                queue.offer(i);
            }
        }
        // bfs outdegree
        while (!queue.isEmpty()) {
            Integer cur = queue.poll();
            count++;
            // for all neighbor, indegree - 1, and check == 0;
            if (!neighbors.containsKey(cur)) {
                continue;
            }
            for (int nei : neighbors.get(cur)) {
                if (indegree.containsKey(nei)) {
                    indegree.put(nei, indegree.get(nei) - 1);
                }
                if (indegree.get(nei) == 0) {
                    queue.offer(nei);
                }
            }  
        }
        return count == numCourses;
    }
}

```

#### Relevant questions

* https://leetcode.com/problems/course-schedule/
* https://leetcode.com/problems/course-schedule-ii/
* https://leetcode.com/problems/sort-items-by-groups-respecting-dependencies/
* https://leetcode.com/problems/alien-dictionary/
* https://leetcode.com/problems/sequence-reconstruction/
* https://leetcode.com/problems/longest-increasing-path-in-a-matrix/
* https://leetcode.com/problems/minimum-height-trees/
