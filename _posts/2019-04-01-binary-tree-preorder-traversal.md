---
title: "Binary Tree Preorder Traversal"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description](https://leetcode.com/problems/binary-tree-preorder-traversal/)
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
    def preorderTraversal(self, root: 'TreeNode') -> 'List[int]':
        vals = []
        if root:
            vals.append(root.val)
            vals += self.preorderTraversal(root.left)
            vals += self.preorderTraversal(root.right)
        return vals
```
I am lucky to get
> Runtime: **36 ms**, faster than **76.74%** of Python3 online submissions for Binary Tree Preorder Traversal.

### Time Complexity
$$O(n)$$, where $$n$$ is the number of tree nodes.