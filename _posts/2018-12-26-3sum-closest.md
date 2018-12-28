---
title: "3Sum Closest"
tags: [LeetCode, Python3]
categories: LeetCode
toc: true
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

        # Recursively find smallest/largest index of the
        # least number in curr_n (0, 1, 2 or 3) numbers 
        # that sum up to target.
        def closest(curr_target, curr_n, lo=0):
            nonlocal nums, top, target, min_diff, three_sum

            if curr_n == 0:
                if abs(curr_target) < min_diff:
                    min_diff = abs(curr_target)
                    three_sum = target - curr_target
                return
            
            next_n = curr_n - 1
            largest = len(nums) - curr_n
            largest = bisect(
                nums, curr_target // curr_n,
                lo, largest)
            smallest = bisect_left(
                nums, curr_target - top[next_n], 
                lo, largest) - 1
            smallest = max(smallest, lo)

            for i in range(smallest, largest + 1): 
                if min_diff == 0:
                    return
                next_target = curr_target - nums[i]
                closest(next_target, next_n, i + 1)

        closest(target, 3)
        return three_sum
```
I am lucky to get
> Runtime: **52 ms**, faster than **98.13%** of Python3 online submissions for 3Sum Closest.

## Variants

### Two pointers
Similar to [3sum's two pointers approach](https://siyuangong.com/leetcode/2018/12/22/3sum/#section-2). [sample](https://github.com/qiyuangong/leetcode/blob/master/python/016_3Sum_Closest.py)