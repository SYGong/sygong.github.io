---
title: "[leetCode][python3] Multiply Strings"
---

## From leetCode
[problem description](https://leetcode.com/problems/multiply-strings/description/)
/
No solution provided

## Solution in python3
```python
class Solution(object):
    def multiply(self, num1, num2):
        """
        :type num1: str
        :type num2: str
        :rtype: str
        """
        l1, l2 = map(len, [num1, num2])
        lp = l1 + l2   
        product = [0] * lp 
        # product[0] for possible carry
        for i in range(l1):
            for j in range(l2):
                product[i + j + 1] += int(num1[i]) * int(num2[j])
        for i in reversed(range(lp)):    
                product[i - 1] += product[i] // 10
                product[i] %= 10
        while len(product) > 1 and product[0] == 0:
            product.pop(0)
        return "".join(map(str, product))
```

## Variants

### `return str(int(num1) * int(num2))`
You must not use `int` or `eval`, but leetCode will not prevent you get following results

|---------------------+--------------+-----------|
| Solution            | Runtime (ms) | Beat %    |
|---------------------| -----------: | --------: |
| our complicated one | 164          | 45.10     |
| `eval()`            | 100          | 57.12     |
| `int()`             | 40           | **99.87** |
and 99.87% basically means everyone.
