---
title: "Valid Parentheses"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description](https://leetcode.com/problems/unique-binary-search-trees-ii/)
/
[solution](https://leetcode.com/problems/valid-parentheses/solution/)

## Solution in Python3
```python
class Solution:
    def isValid(self, s: str) -> bool:
        pairs = {
            '(': ')',
            '{': '}', 
            '[': ']'
        }
        stack = []
        for c in s:
            if c in pairs:
                stack.append(c)
            elif c in pairs.values():
                if not stack or pairs[stack.pop()] != c:
                    return False
        return not stack
```
I am lucky to get
> Runtime: **36 ms**, faster than **86.12%** of Python3 online submissions for Valid Parentheses.

### Time Complexity
$$O(l)$$, where $$l$$ is the length of `s`.

*[BST]: Binary Search Tree