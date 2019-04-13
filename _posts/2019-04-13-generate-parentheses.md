---
title: "Generate Parentheses"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description](https://leetcode.com/problems/generate-parentheses/)
/
[solution](https://leetcode.com/problems/generate-parentheses/solution/)

## Solution in Python3
```python
class Solution:    
    def generateParenthesis(self, n: int) -> List[str]:
        combs = [['']] + [[] for i in range(n)]
        for i in range(1, n + 1):          
            for j in range(i):
                for c1 in combs[j]:
                    for c2 in combs[i - j - 1]:
                        combs[i].append('(' + c1 + ')' + c2)
        return combs[n]
```
I am lucky to get
> Runtime: **40 ms**, faster than **83.35%** of Python3 online submissions for Generate Parentheses.

{::comment}
### Time Complexity
$$O(l)$$, where $$l$$ is the length of `s`.
{:/comment}

*[BST]: Binary Search Tree