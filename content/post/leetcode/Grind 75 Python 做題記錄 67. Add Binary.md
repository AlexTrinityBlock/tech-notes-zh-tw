---
title: "Grind 75 Python 做題記錄 67. Add Binary"
date: 2025-10-11T10:10:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 67. Add Binary

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/add-binary/description/)

```python
class Solution:
  def addBinary(self, a: str, b: str) -> str:
    # 1. int(a, 2): 將二進位字串 'a' 轉為十進位整數
    # 2. int(b, 2): 將二進位字串 'b' 轉為十進位整數
    # 3. ... + ...: 將兩個十進位整數相加
    # 4. bin(...): 將相加後的結果轉為二進位字串 (例如 '0b100')
    # 5. [2:]: 切片，移除前綴 '0b'
    return bin(int(a,2)+int(b,2))[2:]
```