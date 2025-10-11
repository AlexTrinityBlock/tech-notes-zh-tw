---
title: "Grind 75 Python 做題記錄 1. Two Sum"
date: 2025-10-11T10:11:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 1. Two Sum

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/two-sum/description/)

```python
# enumerate
class Solution:
  def twoSum(self, nums: List[int], target: int) -> List[int]:
    # 建立快取 key 為數值差值，Value 為 index
    cache: dict = dict()
    # 遍歷 nums
    for k,v in enumerate(nums):
      # 找到差值
      diff:int = target - v
      # 假如 v 在 cache 中，則回傳
      if v in cache: return [k, cache[v]]
      # 紀錄當前差值與索引
      cache[diff] = k
    # 回傳空 List
    return []
```

## 口訣

建立快取存K-V，K為差值V索引

遍歷序列找差值，目標減去當前值

如當前值在快取，回傳當前和差值索引

將差值與索引存快取，差值為K索引V

迴圈完畢空序列