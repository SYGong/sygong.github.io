---
title: "Unique Binary Search Trees II"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description](https://leetcode.com/problems/unique-binary-search-trees-ii/)
/
no solution provided

## Solution in Python3
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def generateTrees(self, n: int) -> List[TreeNode]:
        range_trees = {}

        def gen(s = 1, e):
            nonlocal range_trees
            if (s, e) not in range_trees:
                trees = []
                for i in range(s, e + 1):
                    for l in gen(s, i - 1):
                         for r in gen(i + 1, e):
                            tree = TreeNode(i)
                            tree.left = l 
                            tree.right = r
                            trees.append(tree)                            
                range_trees[(s, e)] = trees        
            return range_trees[(s, e)] or [None]  # (s = 1, e = 0)

        return gen(n) if n > 0 else []  # n = 0
```
I am lucky to get
> Runtime: **60 ms**, faster than **82.93%** of Python3 online submissions for Unique Binary Search Trees II.
> Memory Usage: **14 MB**, less than **76.79%** of Python3 online submissions for Unique Binary Search Trees II.

### Time Complexity
$$O(n!)$$.

*[BST]: Binary Search Tree