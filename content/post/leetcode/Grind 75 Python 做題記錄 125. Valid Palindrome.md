---
title: "Grind 75 Python 做題記錄 125. Valid Palindrome"
date: 2025-10-11T10:16:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 125. Valid Palindrome

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/valid-palindrome/description/)

```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        # 取得統一小寫，並且去除標點的字串
        clean_string : str = "".join(char.lower() for char in s if char.isalnum())
        # 檢查字串是否等於反轉後的字串
        return clean_string == clean_string[::-1]
```