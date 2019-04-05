---
title: "Search in a Binary Search Tree"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description](https://leetcode.com/problems/search-in-a-binary-search-tree/)
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
    def searchBST(self, root: TreeNode, val: int) -> TreeNode:
        if not root:
            return None
        elif val > root.val:
            return self.searchBST(root.right, val)
        elif val < root.val:
            return self.searchBST(root.left, val)
        else:
            return root           
```
I am lucky to get
> Runtime: **84 ms**, faster than **71.59%** of Python3 online submissions for Search in a Binary Search Tree.

### Time Complexity
$$O(h)$$, where $$h$$ is the height of the tree.