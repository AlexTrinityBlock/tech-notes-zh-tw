---
title: "Grind 75 Python 做題記錄 121. Best Time to Buy and Sell Stock"
date: 2025-10-11T10:15:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 121. Best Time to Buy and Sell Stock

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/)

```python
import math
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        # 定義最小價格
        min_price:int = math.inf 
        # 定義最大收益
        max_profix:int = 0

        # 遍歷價格
        for current_price in prices:
            # 假如當前是最小價格，更新最小價格
            if current_price < min_price:
                min_price = current_price
            # 否則確認是否更新最大獲益
            elif max_profix < current_price - min_price:
                max_profix = current_price - min_price
        # 回傳最大獲益
        return max_profix
```