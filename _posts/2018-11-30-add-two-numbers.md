---
title: "Add Two Numbers"
tags: [LeetCode, Python3]
categories: leetcore
---

## From LeetCode
[problem description](https://leetcode.com/problems/add-two-numbers/description/)
/
[solution in java](https://leetcode.com/problems/add-two-numbers/solution/)

## Solution in Python3
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def addTwoNumbers(self, l1, l2):
        """
        :type l1: ListNode
        :type l2: ListNode
        :rtype: ListNode
        """
        eval_ = lambda node: 0 if node is None else node.val
        next_ = lambda node: None if node is None else node.next
        curr = dummy_head = ListNode(0)  
        carry = 0
        while l1 or l2 or carry:
            sum_ = eval_(l1) + eval_(l2) + carry
            curr.next = ListNode(sum_ % 10)
            curr = curr.next
            l1 = next_(l1)
            l2 = next_(l2)
            carry = sum_ // 10
        return dummy_head.next
```
I am lucky to get
> Runtime: **116 ms**, faster than **98.72%** of Python3 online submissions for Add Two Numbers.

### Time Complexity
$$O(l_1 + l_2)$$, where $$l_1$$ and $$l_2$$ are the length of `l1` and `l2`, respectively.

## Variants

### Without "dummy"
Initialize head at the first iteration. [sample](https://www.geeksforgeeks.org/add-two-numbers-represented-by-linked-lists/)

### Further refactoring
- Combine `eval_` and `next_`, or
- initialize `curr_nodes = [dummy_head, l1, l2]` then do `curr_nodes = map(next_, curr_nodes)` at each iteration.