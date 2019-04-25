---
title: "Two City Scheduling"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description](https://leetcode.com/problems/two-city-scheduling/)
/
no solution provided

## Solution in Python3
```python
class Solution:
    def twoCitySchedCost(self, costs: List[List[int]]) -> int:        
        return (
            sum(
                # Baseline: fly B
                map(lambda x : x[1], costs)
            )
            + sum(
                sorted(
                    # Cost reduced if fly A
                    map(lambda x : x[0] - x[1], costs)  
                )[:len(costs) // 2]  
            )
        )
```
I am lucky to get
> Runtime: **36 ms**, faster than **100.00%** of Python3 online submissions for Two City Scheduling.

> Memory Usage: **13.0 MB**, less than **100.00%** of Python3 online submissions for Two City Scheduling.

### Time Complexity
$$O(N)$$, where $$2N$$ is the number of people.

*[BST]: Binary Search Tree