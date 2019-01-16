---
title: "Remove Nth Node From End of List"
tags: [LeetCode, Python3]
categories: leetcore
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
        curr_node = head
        for i in range(n):
            curr_node = curr_node.next
        
        # List has exactly n nodes.
        if not curr_node:
            return head.next

        # Right now, head is the (n+1)th node from curr_node which
        # is not None.
        np1th_from_curr = head

        while curr_node.next:
            curr_node = curr_node.next
            np1th_from_curr = np1th_from_curr.next
        np1th_from_curr.next = np1th_from_curr.next.next
        return head
```
I am lucky to get
> Runtime: **60 ms**, faster than **98.02%** of Python3 online submissions for Remove Nth Node From End of List.

### Time Complexity
$$O(l)$$, where $$l$$ is the length of linked list.
