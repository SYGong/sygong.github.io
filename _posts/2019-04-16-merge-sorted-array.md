---
title: "Merge Sorted Array"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description](https://leetcode.com/problems/merge-sorted-array/)
/
no solution provided

## Solution in Python3
```python
class Solution:
    def merge(
            self, 
            nums1: List[int], 
            m: int, 
            nums2: List[int], 
            n: int
        ) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        # Move largest number to the back of nums1.
        p1 = m - 1
        p2 = n - 1
        p = m + n - 1  
        while p1 >=0 and p2 >= 0:
            if nums1[p1] >= nums2[p2]:
                nums1[p] = nums1[p1]
                p1 -= 1
            else:
                nums1[p] = nums2[p2]
                p2 -= 1
            p -= 1
        while p2 >= 0:
            nums1[p] = nums2[p2]
            p2 -= 1
            p -= 1
```
I am lucky to get
> Runtime: **40 ms**, faster than **76.25%** of Python3 online submissions for Merge Sorted Array.

### Time Complexity
$$O(n + m)$$.


*[BST]: Binary Search Tree