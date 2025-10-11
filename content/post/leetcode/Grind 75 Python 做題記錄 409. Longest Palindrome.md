---
title: "Grind 75 Python 做題記錄 409. Longest Palindrome"
date: 2025-10-11T10:07:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 409. Longest Palindrome

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/longest-palindrome/description/)

```python
import collections

class Solution:
    def longestPalindrome(self, s: str) -> int:
        # 用 collections.Counter(s) 取得每個字元出現次數建立成 dict()
        # 用 .values() 取得值
        # 並且只取出現為奇數的字元
        # 計算奇數字元數量
        odds_nums = sum(v % 2 for v in collections.Counter(s).values())
        # 取得字串長度，然後減去奇數字元的數量，由於奇數字元在回文中只能有一個，
        # 所以用 int(bool(odds_nums)) 判斷，如果奇數字元大於0，則加上 1，如果沒有則減去 1
        return len(s) - odds_nums + int(bool(odds_nums))
```