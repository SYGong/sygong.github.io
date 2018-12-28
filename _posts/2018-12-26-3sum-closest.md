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

        # Compute top[i] the sum of largest i numbers
        top = [
            0, 
            nums[-1], 
            nums[-1] + nums[-2]
        ]

        min_diff = float('inf')
        three_sum = 0

        # Denotes the least one of num_ints (1,2,3...)
        # integers by x, this function return
        # smallest/largest index of x.
        def least_range(sum_, num_ints, lo=0):
            nonlocal cumu_max, nums
            num_ints_remain = num_ints - 1
            most_i = bisect(
                nums, sum_ // num_ints,
                lo, len(nums) - num_ints)
            least_i = bisect_left(
                nums, sum_ - cumu_max[num_ints_remain], 
                lo, len(nums) - num_ints) - 1

            least_i = max(least_i, lo)
            return least_i, most_i+1

        # Consider smallest number in triplets
        a0, a1 = least_range(target, 3)
        for i in range(a0, a1):
            two_sum = target - nums[i]
            b0, b1 = least_range(two_sum, 2, i + 1)
            for j in range(b0, b1):
                complement = two_sum - nums[j]
                c0, c1 = least_range(complement, 1, j + 1)
                for w in nums[c0:c1]:
                    diff = abs(complement - w)
                    if diff == 0:
                        return nums[i] + nums[j] + w
                    elif diff < min_diff:
                        min_diff = diff
                        three_sum = nums[i] + nums[j] + w
        return three_sum
```
I am lucky to get
> Runtime: **316 ms**, faster than **99.78%** of Python3 online submissions for 3Sum.

## Variants

### Two pointers


### Sum up to arbitrary `target`
It is not hard to make our program more general, for example
```diff
-           if v < 0:  # Only when v is smallest
-               two_sum = -v
+           if v * 3 < target:  # Only when v is smallest
+               two_sum = target - v
```
This is not the only piece needs modification, but you get the idea. [sample1](https://github.com/SYGong/leetcode/blob/3sum-counter/3sum.py) [sample2](https://www.geeksforgeeks.org/unique-triplets-sum-given-value/)