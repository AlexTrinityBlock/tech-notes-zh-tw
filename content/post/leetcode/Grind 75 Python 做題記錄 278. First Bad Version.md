---
title: "Grind 75 Python 做題記錄 278. First Bad Version"
date: 2025-10-11T10:04:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 278. First Bad Version

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/first-bad-version/description/)

## 答題

```python
# The isBadVersion API is already defined for you.
# def isBadVersion(version: int) -> bool:

class Solution:
    def firstBadVersion(self, n: int) -> int:
        # 最初版本號
        left = 1
        # 最終版本號
        right = n

        # 二分搜索條件，右側大於左側
        while right > left:
            # 設定中央值
            mid = (right + left) // 2
            
            # 檢測是否為故障版本，假如是故障版本，故障源頭在版本的左側，或者mid本身就是初始故障版本
            if isBadVersion(mid):
                right = mid
            # 若不是故障版本，故障源頭則在右側
            else:
                left = mid + 1

        # 迴圈結束，left 與 right 為同一數值，回傳一個即可
        return right
```s