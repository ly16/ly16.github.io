---
layout:     post
title:      LeetCode Trie template
subtitle:   Trie in Java and relevant questions
date:       2021-01-06
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---

### Java Template
Trie Template

- time = O(n)
- space = O(n) where n is the length of the longest word

[208. Implement Trie (Prefix Tree)](https://leetcode.com/problems/implement-trie-prefix-tree/)

##### Array version

```java
public class Trie {
    class TrieNode {
        public TrieNode[] children = new TrieNode[26];
        public String word;
    }
    public Trie() {
    }
    TrieNode root = new TrieNode();
    
    /** Inserts a word into the trie. */
    public void insert(String word) {
        char[] array = word.toCharArray();
        TrieNode cur = root;
        for (char c : array) {
            if (cur.children[c - 'a'] == null) {
                cur.children[c - 'a'] = new TrieNode();
            }
            cur = cur.children[c - 'a'];
        }
        cur.word = word;
    }
    
    
    
    /** Returns if the word is in the trie. */
    public boolean search(String word) {
        TrieNode cur = root;
        char[] array = word.toCharArray();
        for (char c : array) {
            if (cur.children[c - 'a'] == null) {
                return false;
            }
            cur = cur.children[c - 'a'];
        }
        return cur.word != null &&  cur.word.equals(word);
    }
    
    /** Returns if there is any word in the trie that starts with the given prefix. */
    public boolean startsWith(String prefix) {
        TrieNode cur = root;
        char[] array = prefix.toCharArray();
        for (char c : array) {
            if (cur.children[c - 'a'] == null) {
                return false;
            }
            cur = cur.children[c - 'a'];
        }
        return true;
    }
}
```

##### Map version

```java
class Trie {

    class TrieNode {
        Map<Character, TrieNode> children;
        String word;
        TrieNode() {
            children = new HashMap<>();
            word = "";
        }
        
    }
    TrieNode root = new TrieNode();
    /** Initialize your data structure here. */
    public Trie() {
        
    }
    
    /** Inserts a word into the trie. */
    public void insert(String word) {
        TrieNode cur = root;
        for (char c : word.toCharArray()) {
            if (!cur.children.containsKey(c)) {
                cur.children.put(c, new TrieNode());
            }
            cur = cur.children.get(c);
        }
        cur.word = word;
    }
    
    /** Returns if the word is in the trie. */
    public boolean search(String word) {
        TrieNode cur = root;
        for (char c : word.toCharArray()) {
            if (!cur.children.containsKey(c)) {
                return false;
            }
            cur = cur.children.get(c);
        }
        return cur.word.equals(word);
    }
    
    /** Returns if there is any word in the trie that starts with the given prefix. */
    public boolean startsWith(String prefix) {
        TrieNode cur = root;
        for (char c : prefix.toCharArray()) {
            if (!cur.children.containsKey(c)) {
                return false;
            }
            cur = cur.children.get(c);
        }
        return true;
    }
}

```

#### Relevant questions

* https://leetcode.com/problems/word-search-ii/
