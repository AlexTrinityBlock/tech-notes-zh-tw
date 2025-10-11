---
title: "Grind 75 Python 做題記錄 242. Valid Anagram"
date: 2025-10-11T10:18:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 242. Valid Anagram

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/valid-anagram/description/)

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        # 假如字串長度不同，回傳 False
        if len(s) != len(t): return False
        # 假如轉換成集合不同，回傳 False  
        s_set:set = set(s)
        if s_set != set(t): return False
        # 假如文字的數量不同，則回傳 False
        for char in s_set:
            if s.count(char) != t.count(char): return False
        return True
```