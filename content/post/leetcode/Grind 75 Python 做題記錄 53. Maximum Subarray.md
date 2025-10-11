---
title: "Grind 75 Python 做題記錄 53. Maximum Subarray"
date: 2025-10-11T10:24:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 Grind 75 Python 做題記錄 53. Maximum Subarray

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/maximum-subarray/description/)


實測起來`if`比`max`快一些。

```python
import math
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        # Kadane's Algorithm 卡登算法
        # 定義全局最大和與局部最大和
        global_max_sum = -math.inf
        local_max_sum = 0 
        # 遍歷序列
        for num in nums:
            # 更新局部最大解
            local_max_sum += num
            # 更新全局最大解
            global_max_sum = local_max_sum if global_max_sum < local_max_sum else global_max_sum
            # 假如小於0，直接歸零，因為負數加上去，局部最大解必定數值變小
            if local_max_sum < 0 : local_max_sum=0
        # 回傳全局
        return global_max_sum
```

## 口訣

> 全局從最小開始，局部則從零開始
> 序列全部遍歷完，更新局部與全局
> 局部與當前求和，全局局部取最大
> 局部若是小於零，歸零後重新開始