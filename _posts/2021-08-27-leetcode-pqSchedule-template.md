---
layout:     post
title:      LeetCode Priority Queue schedule template
subtitle:   Use heap to schedule tasks
date:       2021-08-27
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---

### Java Template
Use priority Queue to schedule tasks
1. Use two priority queues to present servers in using and available
2. Each time new task comes, move using to available, and then assign server from available to tasks.

- time = O(nlogn)
- space = O(n)

[1882. Process Tasks Using Servers](https://leetcode.com/problems/process-tasks-using-servers/)

```java
class Solution {

    public int[] assignTasks(int[] servers, int[] tasks) {
        // <weight, index>
        PriorityQueue<int[]> available = new PriorityQueue<>((a, b) -> (a[0] == b[0] ? a[1] - b[1] : a[0] - b[0]));
        // <time, weight, index>
        PriorityQueue<int[]> using = new PriorityQueue<>((a, b) -> {
            if (a[0] == b[0]) {
                if (a[1] == b[1]) {
                    return a[2] - b[2];
                } 
                return a[1] - b[1];
            }
            return a[0] - b[0];
        });
        int[] res = new int[tasks.length];
        Queue<Integer> q = new LinkedList<>();
        
        for (int i = 0; i < servers.length; i++) {
            available.offer(new int[]{servers[i], i});
        }
        
        for (int i = 0; i < tasks.length; i++) {
            q.offer(i);
            // put using to available
            while (!using.isEmpty() && using.peek()[0] <= i) {
                int[] toAvailable = using.poll();
                available.offer(new int[]{toAvailable[1], toAvailable[2]});
            }
            // assign tasks from available
            while (!q.isEmpty() && !available.isEmpty()) {
                int[] server = available.poll();
                int t = q.poll();
                res[t] = server[1];
                using.offer(new int[] {tasks[t] + i, server[0], server[1]});
            }
        }
        
        // tasks in the queue waiting for servers in using 
        while (!q.isEmpty()) {
            int[] server = using.poll();
            int task = q.poll();
            res[task] = server[2];
            using.offer(new int[] {server[0] + tasks[task], server[1], server[2]});
        }
        return res;
    }
}
```

#### Relevant questions

* https://leetcode.com/problems/process-tasks-using-servers/
* https://leetcode.com/problems/the-number-of-the-smallest-unoccupied-chair/
* https://leetcode.com/problems/task-scheduler/
