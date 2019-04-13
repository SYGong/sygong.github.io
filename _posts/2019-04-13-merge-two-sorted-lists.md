---
title: "Merge Two Sorted Lists"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description](https://leetcode.com/problems/merge-two-sorted-lists/)
/
no solution provided

## Solution in Python3
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        if not l2:
            return l1
        if not l1:
            return l2
        if l1.val < l2.val:
            l1.next = self.mergeTwoLists(l1.next, l2)
            return l1
        else:
            l2.next = self.mergeTwoLists(l1, l2.next)
            return l2
```
I am lucky to get
> Runtime: **44 ms**, faster than **87.36%** of Python3 online submissions for Merge Two Sorted Lists.

### Time Complexity
$$O(\max(l_1, l_2))$$, where $$l_1$$ and $$l_2$$ are the length of `l1` and `l2`, respectively.

## Variants

### Iteration
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        if not l2:
            return l1
        if not l1:
            return l2
        if l1.val < l2.val:
            l1.next = self.mergeTwoLists(l1.next, l2)
            return l1
        else:
            l2.next = self.mergeTwoLists(l1, l2.next)
            return l2
```
I got:
> Runtime: **44 ms**, faster than **87.36%** of Python3 online submissions for Merge Two Sorted Lists.

Not a surprise since time complexity is the same as the recursive solution above. Memory usage could be less, though.


*[BST]: Binary Search Tree