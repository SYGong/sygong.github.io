---
title: "3Sum Closest"
tags: [LeetCode, Python3]
categories: leetcore
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

        # Let top[i] be the sum of largest i numbers.
        top = [
            0,
            nums[-1],
            nums[-1] + nums[-2]
        ]

        min_diff = float('inf')
        three_sum = 0

        # Find range of the least number in curr_n (0, 1, 2 or 3)
        # numbers that sum up to curr_target, then find range of 
        # 2nd least number and so on by recursion. 
        def closest(curr_target, curr_n, lo=0):
            if curr_n == 0:
                nonlocal min_diff, three_sum
                if abs(curr_target) < min_diff:
                    min_diff = abs(curr_target)
                    three_sum = target - curr_target
                return
            
            next_n = curr_n - 1
            max_i = len(nums) - curr_n
            max_i = bisect(
                nums, curr_target // curr_n,
                lo, max_i)
            min_i = bisect_left(
                nums, curr_target - top[next_n],
                lo, max_i) - 1
            min_i = max(min_i, lo)

            for i in range(min_i, max_i + 1): 
                if min_diff == 0:
                    return
                if i == min_i or nums[i] != nums[i - 1]:
                    next_target = curr_target - nums[i]
                    closest(next_target, next_n, i + 1)

        closest(target, 3)
        return three_sum
```
I am lucky to get
> Runtime: **52 ms**, faster than **98.13%** of Python3 online submissions for 3Sum Closest.

### Time Complexity
$$O(n^2 log{n})$$, where $$n$$ is the number of numbers.
- Binary search function `bisect` takes $$\log{n}$$. 
- The range of last number is $$O(1)$$ since `curr_n` is `1` and `top[next_n]` is `0`. So given 2 numbers, find the last number takes $$\log{n}$$.

{::comment}
- It takes $$O(\log{n})$$ to find a $$O(n)$$ range in each `closest()` call (except last one).
- For each candidate in such range we need to call `closest()` with `next_target`, so `closest(curr_target, ...)` takes $$O(n + \log{n}) = O(n)$$.
{:/comment}

## Variants

### Two pointers
Similar to [3Sum's two pointers approach](https://siyuangong.com/leetcode/2018/12/22/3sum/#two-pointers). [sample](https://github.com/qiyuangong/leetcode/blob/master/python/016_3Sum_Closest.py)