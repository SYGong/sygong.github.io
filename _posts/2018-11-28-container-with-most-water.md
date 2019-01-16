---
title: "Container With Most Water"
tags: [LeetCode, Python3]
categories: leetcore
---

## From LeetCode
[problem description](https://leetcode.com/problems/container-with-most-water/description/)
/
[solution in java](https://leetcode.com/problems/container-with-most-water/solution/#approach-2-two-pointer-approach)

## Solution in Python3
```python
class Solution(object):
    def maxArea(self, height):
        """
        :type height: List[int]
        :rtype: int
        """
        l = 0                # Left pointer
        r = len(height) - 1  # Right pointer 
        max_area = 0
        while l < r:
            current_area = min(height[l], height[r]) * (r - l)
            max_area = max(current_area, max_area)
            if height[l] < height[r]:
                l += 1
            else:
                r -= 1
        return max_area
```
I am lucky to get
> Runtime: **72 ms**, faster than **98.75%** of Python3 online submissions for Container With Most Water.

### Time Complexity
$$O(n)$$, where $$n$$ is the number of vertical bars, i.e., `len(height)`.

## Variants

### Consider the case that `height[l] == height[r]`
Move both pointers. [sample](http://bangbingsyb.blogspot.com/2014/11/leetcode-container-with-most-water.html)
