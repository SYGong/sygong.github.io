---
title: "Lowest Common Ancestor of a Binary Search Tree"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/)
/
[solution](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/solution/)

## Solution in Python3
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def lowestCommonAncestor(self, root: 'TreeNode', p: 'TreeNode', q: 'TreeNode') -> 'TreeNode':
        a = root.val - p.val
        b = root.val - q.val
        if a * b > 0:
            if a > 0:
                return self.lowestCommonAncestor(root.left, p, q)
            else:
                return self.lowestCommonAncestor(root.right, p, q)
        return root          
```
I am lucky to get
> Runtime: **88 ms**, faster than **72.89%** of Python3 online submissions for Lowest Common Ancestor of a Binary Search Tree.

### Time Complexity
$$O(n)$$, where $$n$$ is the number of tree nodes.