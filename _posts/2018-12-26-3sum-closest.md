---
title: "3Sum Closest"
tags: [LeetCode, Python3]
categories: LeetCode
---

## From LeetCode
[problem description](https://leetcode.com/problems/3sum-closest/)
/
no solution provided

## Solution in Python3
```python
from bisect import bisect, bisect_left

class Solution:
    def threeSumClosest(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: int
        """
        nums = sorted(nums)

        # Let top[i] be the sum 
        # of largest i numbers.
        top = [
            0,
            nums[-1],
            nums[-1] + nums[-2]
        ]

        min_diff = float('inf')
        three_sum = 0

        # Recursively find smallest/largest index of
        # least number in numbers that sum up to target.
        def closest(curr_target, num_ints, lo=0):
            nonlocal nums, top, target, min_diff, three_sum

            if num_ints == 0:
                if abs(curr_target) < min_diff:
                    min_diff = abs(curr_target)
                    three_sum = target - curr_target
                return
            
            largest = len(nums) - num_ints
            largest = bisect(
                nums, curr_target // num_ints,
                lo, largest)
            smallest = bisect_left(
                nums, curr_target - top[num_ints - 1], 
                lo, largest) - 1
            smallest = max(smallest, lo)

            for i in range(smallest, largest + 1): 
                if min_diff == 0:
                    return
                next_target = curr_target - nums[i]
                closest(next_target, num_ints - 1, i + 1)

        closest(target, 3)
        return three_sum
```
I am lucky to get
> Runtime: **52 ms**, faster than **98.13%** of Python3 online submissions for 3Sum.

## Variants

### Two pointers
Similar to 3sum's two pointers approach. [sample](https://github.com/qiyuangong/leetcode/blob/master/python/016_3Sum_Closest.py)