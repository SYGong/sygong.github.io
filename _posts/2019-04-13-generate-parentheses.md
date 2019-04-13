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

        # combs[m] will be a list of all the valid combination
        # of m pairs of parenthesis
        combs = [['']] + [[] for i in range(n)]  
         
        for i in range(1, n + 1):          
            for j in range(i):
                for _in in combs[j]:
                    for _out in combs[i - j - 1]:
                        combs[i].append('(' + _in + ')' + _out)
        return combs[n]
```
I am lucky to get
> Runtime: **40 ms**, faster than **83.35%** of Python3 online submissions for Generate Parentheses.

### Time Complexity
$$O(\frac{4^n}{\sqrt{n}})$$.

*[BST]: Binary Search Tree