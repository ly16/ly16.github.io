---
layout:     post
title:      LeetCode UnionFind template
subtitle:   UnionFind in Java and relevant questions
date:       2021-02-02
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---

### UF Java Template


##### Quick Union
- time = O(n^2) each union is O(n)
  - if connect n items, the total time = O(n^2)
- space = O(n)


```java
class UF {
    private int count;
    private int[] parent;

    public UF(int n) {
        this.count = n;
        parent = new int[n];
        for (int i = 0; i < n; i++)  // time = O(n)
            parent[i] = i;
    }
    
    public void union(int p, int q) {
      int rootP = find(p);
      int rootQ = find(q);
      if (rootP == rootQ)
          return;
      parent[rootP] = rootQ;
      // parent[rootQ] = rootP same
      count--; 
   }

    private int find(int x) { // time = O(n)
        while (parent[x] != x)
            x = parent[x];
        return x;
    }   
}
```

##### Weighted Quick Union with Path Compression

- time = O(n + n lg*n) = O(n) 
  - where lg*n is Ackerman function, very close to 1. n is the item need to do union.
- space = O(n)

```java
class UF {
    private int count;
    private int[] parent;
    // weight of each root
    private int[] size;

    public UF(int n) {
        this.count = n;
        parent = new int[n];
        size = new int[n];
        for (int i = 0; i < n; i++) { // time = O(n)
            parent[i] = i;
            size[i] = 1;
        }
    }

    public void union(int p, int q) { // time = O(1)
        int rootP = find(p);
        int rootQ = find(q);
        if (rootP == rootQ)
            return;

        if (size[rootP] > size[rootQ]) { // MST, put smaller tree under the larger tree
            parent[rootQ] = rootP;
            size[rootP] += size[rootQ];
        } else {
            parent[rootP] = rootQ;
            size[rootQ] += size[rootP];
        }
        count--;
    }

    public boolean connected(int p, int q) {
        int rootP = find(p);
        int rootQ = find(q);
        return rootP == rootQ;
    }

    private int find(int x) { //  time = O(1)
        while (parent[x] != x) {
            parent[x] = parent[parent[x]]; // path compression
            x = parent[x];
        }
        return x;
    }
}

```


##### HashMap version of unionFind
[Leetcode 721](https://leetcode.com/problems/accounts-merge/)

```java
    class UF {
        Map<String, String> parentMap;
        Map<String, Integer> sizeMap;
        UF() {
            parentMap = new HashMap<>();
            sizeMap = new HashMap<>();
        }

        void union(String s1, String s2) {
            String p1 = find(s1);
            String p2 = find(s2);

            if(p1.equals(p2)) {
                return;
            }
            if (sizeMap.get(p1) > sizeMap.get(p2)) {
                parentMap.put(p2, p1);
                sizeMap.put(p1, sizeMap.get(p1) + sizeMap.get(p2));
            } else {
                parentMap.put(p1, p2);
                sizeMap.put(p2, sizeMap.get(p2) + sizeMap.get(p1));
            }
        }

        String find(String x) {
            if (!parentMap.containsKey(x)) {
                parentMap.put(x, x);
                sizeMap.put(x, 1);
                return x;
            }
            while (!x.equals(parentMap.get(x))) {
                parentMap.put(x, parentMap.get(parentMap.get(x)));
                x = parentMap.get(x);
            }
            return x;
        }
    }
```


#### Relevant questions & reference


* [refer1](https://mp.weixin.qq.com/s/gUwLfi25TYamq8AJVIopfA)
* [refer2](https://blog.csdn.net/Yaokai_AssultMaster/article/details/78888846)
* https://leetcode.com/problems/lexicographically-smallest-equivalent-string/
* https://leetcode.com/problems/connecting-cities-with-minimum-cost/
* https://leetcode.com/problems/the-earliest-moment-when-everyone-become-friends/
* https://leetcode.com/problems/redundant-connection/
* https://leetcode.com/problems/number-of-provinces/
* https://leetcode.com/problems/number-of-connected-components-in-an-undirected-graph/
* https://leetcode.com/problems/most-stones-removed-with-same-row-or-column/
* https://leetcode.com/problems/number-of-operations-to-make-network-connected/
* https://leetcode.com/problems/accounts-merge/
* https://leetcode.com/problems/couples-holding-hands/
* https://leetcode.com/problems/optimize-water-distribution-in-a-village/
