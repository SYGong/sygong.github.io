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
        dist_cells = {}
        max_dist = max(r0, R - 1 - r0) + max(c0, C - 1 - c0)
        for i in range(R):
            for j in range(C):
                dist = abs(r0 - i) + abs(c0 - j)
                dist_cells.setdefault(dist, [])
                dist_cells[dist].append([i, j])
        cells = []
        for dist in range(max_dist + 1):
            cells += dist_cells[dist]
        return cells
```
I am lucky to get
> Runtime: **272 ms**, faster than **74.55%** of Python3 online submissions for Matrix Cells in Distance Order.

> Memory Usage: **15.1 MB**, less than **100.00%** of Python3 online submissions for Matrix Cells in Distance Order.

### Time Complexity
$$O(n)$$, where $$n$$ = `R * C`.

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
Time complexity will be $$O(n\log(n))$$, where $$n$$ = `R * C`. In the contest I did this way for its simplicity. I got

> Runtime: **264 ms**, faster than **90.23%** of Python3 online submissions for Matrix Cells in Distance Order.

Not bad at all.

*[BST]: Binary Search Tree