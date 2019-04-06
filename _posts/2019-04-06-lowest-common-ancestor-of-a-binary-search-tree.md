---
title: "Lowest Common Ancestor of a Binary Search Tree"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/)
/
[solution][solution_link]

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
        if p.val < root.val and q.val < root.val:
            return self.lowestCommonAncestor(root.left, p, q)
        elif p.val > root.val and q.val > root.val:
            return self.lowestCommonAncestor(root.right, p, q)
        return root       
```
I am lucky to get
> Runtime: **88 ms**, faster than **72.89%** of Python3 online submissions for Lowest Common Ancestor of a Binary Search Tree.

### Time Complexity
$$O(h)$$, where $$h$$ is the height the tree.

**Note**: [Leetcode's solution][solution_link] says the complexity is $$O(n)$$, where $$n$$ is the number of nodes. Well, in the **worst** tree, $$O(h) = O(n)$$. 
{: .notice}

[solution_link]: https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/solution/