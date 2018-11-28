---
title: "[leetCode][python3] Container With Most Water"
---

## From leetCode
[problem description](https://leetcode.com/problems/container-with-most-water/description/)
/
[solution in java](https://leetcode.com/problems/container-with-most-water/solution/#approach-2-two-pointer-approach)


## Solution in python3
```python
class Solution(object):
class Solution:
    def maxArea(self, height):
        """
        :type height: List[int]
        :rtype: int
        """
        l, r = 0, len(height) - 1 #left pointer and right pointer 
        max_area = 0
        while l < r:
            current_area = min(height[l], height[r]) * (r - l)
            max_area = max(current_area, max_area)
            if height[l] < height[r]:
                l += 1
            else :
                r -= 1
        return max_area
```

## Variants

### Consider the case that `height[l] == height[r]`
Move both pointer towards each other. [code example](http://bangbingsyb.blogspot.com/2014/11/leetcode-container-with-most-water.html)