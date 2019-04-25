---
title: "Matrix Cells in Distance Order"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description](https://leetcode.com/problems/matrix-cells-in-distance-order/)
/
no solution provided

## Solution in Python3
```python
class Solution:
    def allCellsDistOrder(
            self, 
            R: int, 
            C: int, 
            r0: int, 
            c0: int
        ) -> List[List[int]]:
        points = {}
        max_dis = max(r0, R - r0) + max(c0, C - c0)
        for i in range(R):
            for j in range(C):
                d = abs(r0 - i) + abs(c0 - j)
                points.setdefault(d, [])
                points[d].append((i, j))
        ans = []
        for key in range(maxd + 1):
            ans.extend(points[key])
        return ans
```
I am lucky to get
> Runtime: **36 ms**, faster than **100.00%** of Python3 online submissions for Two City Scheduling.

> Memory Usage: **13.0 MB**, less than **100.00%** of Python3 online submissions for Two City Scheduling.

### Time Complexity
$$O(N)$$, where $$2N$$ is the number of people.

## Variant

### (Comparison) Sort
```python
class Solution:
    def allCellsDistOrder(
            self, 
            R: int, 
            C: int, 
            r0: int, 
            c0: int
        ) -> List[List[int]]:
        return sorted(
            [[i, j] for i in range(R) for j in range(C)], 
            key = lambda x : abs(x[1] - c0) + abs(x[0] - r0)
        )
```
Time complexity will be $$O(n\log(n))$$, where $$n$$ = `R * C`. In the contest I solved the problem in this way for simplicity.

*[BST]: Binary Search Tree