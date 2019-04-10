---
title: "Find Mode in Binary Search Tree"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description](https://leetcode.com/problems/find-mode-in-binary-search-tree/)
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
    def findMode(self, root: TreeNode) -> List[int]:
        modes = []
        max_freq = 0
        curr_mode = None
        curr_freq = 0
        
        def traverse(node):            
            if node:                
                traverse(node.left)
                
                nonlocal curr_mode, curr_freq, modes, max_freq
                if curr_mode != node.val: 
                    curr_mode = node.val
                    curr_freq = 1                    
                else:
                    curr_freq += 1
                if curr_freq > max_freq:
                    max_freq = curr_freq
                    modes = [curr_mode]             
                elif curr_freq == max_freq:
                    modes.append(curr_mode)
                                        
                traverse(node.right)
        
        traverse(root)
            
        return modes    
```
**Note**: This (in-order) traversal of BST will visit values in ascending order. 
{: .notice}

I am lucky to get
> Runtime: **64 ms**, faster than **88.47%** of Python3 online submissions for Find Mode in Binary Search Tree.

### Time Complexity
$$O(n)$$, where $$n$$ is the number of tree nodes.

*[BST]: Binary Search Tree