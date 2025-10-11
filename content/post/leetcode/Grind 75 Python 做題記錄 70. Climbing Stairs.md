---
title: "Grind 75 Python 做題記錄 70. Climbing Stairs"
date: 2025-10-11T10:06:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 70. Climbing Stairs

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/climbing-stairs/description/)

```python
class Solution:
  def climbStairs(self, n: int) -> int:
    # 記錄每一層樓梯的步驟數
    way_dict = dict()
    # 初始值
    way_dict[0] = 0
    way_dict[1] = 1
    # 走到二階有一次一階與一次兩階
    way_dict[2] = 2
    # 產生直到 n 階的所有步數
    for i in range(n+1):
      if i <= 2: continue
      # 每一階等於前兩階的可能性相加
      way_dict[i] = way_dict[i - 1] + way_dict[i - 2]
    return way_dict[i]
```