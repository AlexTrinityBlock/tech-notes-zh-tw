---
title: "Grind 75 Python 做題記錄 169. Majority Element"
date: 2025-10-11T10:09:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 169. Majority Element

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/majority-element/description/)

```python
import collections
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        # Boyer-Moore 算法
        # 記數
        count = 0
        # 候選人
        can = None
        # 遍歷 List
        for num in nums:
            # 假如記數為 0，則記錄候選人
            if count == 0: can = num
            # 假如是候選人，則加1，不是候選人則減1
            if num == can:
                count += 1
            else:
                count -= 1
        return can
```