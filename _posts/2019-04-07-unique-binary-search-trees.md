---
title: "Unique Binary Search Trees"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description](https://leetcode.com/problems/unique-binary-search-trees/)
/
no solution provided

## Solution in Python3
```python
class Solution:
    def numTrees(self, n: int) -> int:
        nums = [1]   # 1 unique empty tree
        for i in range(1, n + 1):
            num = 0
            for j in range(i):
                num += nums[j] * nums[i - j - 1]
            nums.append(num)
        return nums[-1]     
```
I am lucky to get
> Runtime: **36 ms**, faster than **70.82%** of Python3 online submissions for  Unique Binary Search Trees.

### Time Complexity
$$O(n^2ln(n))$$.