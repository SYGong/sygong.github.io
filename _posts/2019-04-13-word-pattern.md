---
title: "Word Pattern"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description](https://leetcode.com/problems/word-pattern/)
/
no solution provided

## Solution in Python3
```python
class Solution:
    def wordPattern(self, pattern: str, st: str) -> bool: 
        words = st.split()
        return (
            len(words) == len(pattern) 
            and len(set(pattern)) 
                == len(set(words)) 
                == len(set(zip(words, pattern)))
        )
```
I am lucky to get
> Runtime: **36 ms**, faster than **76.09%** of Python3 online submissions for Word Pattern.

### Time Complexity
$$O(n)$$, where $$n$$ is the number of words.

## Variant
### Dictionary
```python
class Solution:
    def wordPattern(self, pattern: str, st: str) -> bool:
        word_to_pattern = {}
        words = st.split()
        if len(words) != len(pattern):
            return False
        for i, p in enumerate(pattern):
            if words[i] in word_to_pattern:
                if word_to_pattern[words[i]] != p:
                    return False
            else:
                if p in word_to_pattern.values():
                    return False
                word_to_pattern[words[i]] = p
            
        return True
```
> Runtime: **36 ms**, faster than **76.09%** of Python3 online submissions for Word Pattern.

*[BST]: Binary Search Tree