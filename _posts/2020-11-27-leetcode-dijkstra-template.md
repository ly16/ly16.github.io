---
layout:     post
title:      LeetCode Dijkstra template
subtitle:   Dijkstra in Java and relevant questions
date:       2020-11-27
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---

### Java Template
Use priority Queue for BFS

- time = O((E+V)logV) = O(ElogV)
- space = O(V)


```java
class Solution {
    class Pair {
        int val;
        int dist;
        Pair(int val, int dist) {
            this.val = val;
            this.dist = dist;
        }
    }
    public int networkDelayTime(int[][] times, int N, int K) {
        Map<Integer, Integer> map = new HashMap<>();
        Map<Integer, List<Pair>> graph = new HashMap<>();
        for (int[] time : times) {
            if (!graph.containsKey(time[0])) {
                graph.put(time[0], new ArrayList<Pair>());
            }
            graph.get(time[0]).add(new Pair(time[1], time[2]));
        }
        
        PriorityQueue<Pair> pq = new PriorityQueue<>((o1, o2) -> (o1.dist - o2.dist));
        pq.offer(new Pair(K, 0));
        
        while (!pq.isEmpty()) {
            Pair cur = pq.poll();
            if (map.containsKey(cur.val)) {
                continue;
            }
            map.put(cur.val, cur.dist);
            if (!graph.containsKey(cur.val)) {
                continue;
            }
            for (Pair nei : graph.get(cur.val)) {
                pq.offer(new Pair(nei.val, cur.dist + nei.dist));
            }
        }
        
        if (map.size() < N) {
            return -1;
        }
        int res = -1;
        for (int value : map.values()) {
            res = Math.max(res, value);
        }
        return res;
    }
}

```
