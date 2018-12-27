---
title: "3Sum"
tags: [LeetCode, Python3]
categories: LeetCode
---

## From LeetCode
[problem description](https://leetcode.com/problems/3sum/)
/
no solution provided

## Solution in Python3
```python
from collections import Counter
from bisect import bisect, bisect_left

class Solution:
    def threeSumClosest(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: int
        """
        num_freq = Counter(nums)
        nums = sorted(num_freq)  # Sorted unique numbers
        closest_triplet = None
        min_diff = float('inf')

        # Denotes the least one of num_ints (1,2,3...) 
        # integers by x, this function return 
        # smallest/largest index of x.
        def lst(int_list, sum_, num_ints, lo = 0):
            num_ints_remain = num_ints - 1
            if num_ints_remain == 0:
                most_i = bisect(int_list, sum_, lo)
                least_i = most_i - 1
            else:
                least_v = sum_ - num_ints_remain * nums[-1]
                least_i = bisect(int_list, least_v, lo) - 1
                most_v = sum_ // num_ints
                most_i = bisect(int_list, most_v, lo)
            least_i = max(least_i, lo)          
            most_i = min(most_i, len(int_list) - 1)
            return int_list[least_i:most_i], most_i
        
        # Consider smallest number in triplets
        a, a_most = lst(nums, target, 3)
        for i, v in enumerate(a):
            num_freq[v] -= 1
            two_sum = target - v
            b, b_most = lst(nums, two_sum, 2, i)
            for j, u in enumerate(b):
                if num_freq[u]:
                    num_freq[u] -= 1
                    complement = two_sum - u
                    c, c_m = lst(nums, complement, 1, j)
                    for w in c:
                        if num_freq[w]:
                            diff = abs(complement - w)
                            if diff == 0:
                                return [v, u, w]
                            elif diff < min_diff:
                                min_diff = diff
                                closest_triplet = [v, u, w]
                    num_freq[u] += 1            
            num_freq[v] += 1
        return closest_triplet
```
I am lucky to get
> Runtime: **316 ms**, faster than **99.78%** of Python3 online submissions for 3Sum.

## Variants

### Two pointers
```diff
            # When all 3 numbers are different
            if v < 0:  # only when v is smallest
                two_sum = -v

-               # Lower/upper bound of the 
-               # smaller of remaining two.
-               lb = bisect_left(nums, two_sum - max_num, i + 1)
-               ub = bisect(nums, two_sum // 2, lb)
+               # Lower bound for the smaller of remaining two.
+               lb = bisect_left(nums, two_sum - max_num, i + 1)
+               lb = min(lb, len(nums) - 1)
+
+               # Upper bound of the greater of remaining two.
+               ub = bisect(nums, two_sum - nums[lb], lb + 1)
+               ub = min(ub, len(nums) - 1)
                      
-               for u in nums[lb : ub]:
-                   complement = two_sum - u
-                   if complement in num_freq and u != complement:
-                       triplets.append([v, u, complement])
+               while lb < ub:
+                   if nums[lb] + nums[ub] == two_sum:
+                       triplets.append([v, nums[lb], nums[ub]])
+                       lb += 1
+                       ub -= 1
+                   elif nums[lb] + nums[ub] > two_sum:
+                       ub -= 1
+                   else:
+                       lb += 1
        return triplets
```
This solution is not bad, it has:
> Runtime: **808 ms**, faster than **88.99%** of Python3 online submissions for 3Sum.

In case we can't get binary search effortlessly, let `lb = i + 1` and `ub = len(nums) - 1`. This [sample](https://github.com/SYGong/leetcode/blob/3sum-counter/3sum.py) has
> Runtime: **492 ms**, faster than **97.76%** of Python3 online submissions for 3Sum.

Not bad at all.

### Remove duplicated triplets
This problem is difficult only because we need many conditions to keep all triplets are unique (otherwise [code](https://github.com/SYGong/leetcode/blob/23ad10e2549bb2e33e502d43a3b00c7dc40d5544/3sum.py) will be simple). If we handle duplicates seperately, it could be easier to write and read. However, it may not worth the effort to compare triplets given the data structure we have by hand. It will also sacrifice runtime.

### Sum up to arbitrary `target`
It is not hard to make our program more general, for example
```diff
-           if v < 0:  # Only when v is smallest
-               two_sum = -v
+           if v * 3 < target:  # Only when v is smallest
+               two_sum = target - v
```
This is not the only piece needs modification, but you get the idea. [sample1](https://github.com/SYGong/leetcode/blob/3sum-counter/3sum.py) [sample2](https://www.geeksforgeeks.org/unique-triplets-sum-given-value/)