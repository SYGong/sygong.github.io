---
title: "Binary Tree Postorder Traversal"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description](https://leetcode.com/problems/binary-tree-postorder-traversal/)
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
    def postorderTraversal(self, root: 'TreeNode') -> 'List[int]':
        vals = []
        if root:
            vals += self.postorderTraversal(root.left)
            vals += self.postorderTraversal(root.right)
            vals.append(root.val)
        return vals
```
I am lucky to get
> Runtime: **36 ms**, faster than **76.46%** of Python3 online submissions for Binary Tree Postorder Traversal.

### Time Complexity
$$O(n)$$, where $$n$$ is the number of tree nodes.