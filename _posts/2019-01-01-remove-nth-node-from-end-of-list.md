---
title: "Remove Nth Node From End of List"
tags: [LeetCode, Python3]
categories: LeetCode
---

## From LeetCode
[problem description](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)
/
[solution](https://leetcode.com/problems/remove-nth-node-from-end-of-list/solution/)

## Solution in Python3
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def removeNthFromEnd(self, head, n):
        """
        :type head: ListNode
        :type n: int
        :rtype: ListNode
        """
        Np1th_from_curr = head
        curr_node = head
        while curr_node.next:
            curr_node = curr_node.next
            if n > 0:
                n -= 1
            else:
                Np1th_from_curr = Np1th_from_curr.next
        if n > 0:
            head = head.next
        else:
            Np1th_from_curr.next = Np1th_from_curr.next.next
        return head
```

## Variants