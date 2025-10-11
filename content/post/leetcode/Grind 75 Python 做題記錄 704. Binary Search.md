---
title: "Grind 75 Python 做題記錄 704. Binary Search"
date: 2025-10-11T10:19:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 704. Binary Search

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/binary-search/description/)

```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        # 二分搜索的左右指標設定
        left = 0
        right = len(nums)-1
        # 建立循環條件
        while left <= right:
            # 計算中央值
            mid = (left + right)//2
            # 假如中值命中
            if nums[mid] == target:
                return mid
            # 假如中值小於目標
            elif nums[mid] < target:
                # 左側指標向右移動
                left = mid + 1
            # 假如中值大於目標
            else:
                # 右側指標往左移動
                right = mid - 1
        # 都沒命中
        return -1
```