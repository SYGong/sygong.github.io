---
title: "Shortest Distance to a Character"
tags: [LeetCode, Python3]
categories: leetcore
mathjax: true
---

## From LeetCode
[problem description/sulution](https://leetcode.com/problems/shortest-distance-to-a-character/)

## Solution in Python3
```python
class Solution:
    def shortestToChar(self, S: str, C: str) -> List[int]:
        shortest_dist = []
        dist = float('inf')
        for c in S:
            if c == C:
                dist = 0
            else:
                dist += 1
            shortest_dist.append(dist)
        
        dist = float('inf')
        for i in range(len(S) - 1, -1 , -1):
            if S[i] == C:
                dist = 0
            else:
                dist += 1
            shortest_dist[i] = min(shortest_dist[i], dist)

        return shortest_dist    
            
```
I am lucky to get
> Runtime: **48 ms**, faster than **87.25%** of Python3 online submissions for Shortest Distance to a Character.

### Time Complexity
$$O(l)$$, where $$l$$ is the length of `S`.