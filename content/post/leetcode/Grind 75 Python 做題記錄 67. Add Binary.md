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

## 位元加法

```python
class Solution:
  def addBinary(self, a: str, b: str) -> str:
    # 初始化結果列表、進位(carry)和指標(i, j)
    result = []
    carry = 0
    i, j = len(a) - 1, len(b) - 1

    # 迴圈條件：只要任一字串還有位數，或最後還有進位，就繼續
    while i >= 0 or j >= 0 or carry:
      # 處理 a 的當前位數
      if i >= 0:
        carry += int(a[i])
        i -= 1
      
      # 處理 b 的當前位數
      if j >= 0:
        carry += int(b[j])
        j -= 1
      
      # 當前位的結果是 carry % 2
      # 例如：sum = 2 (1+1+0), 2 % 2 = 0
      #       sum = 3 (1+1+1), 3 % 2 = 1
      result.append(str(carry % 2))
      
      # 新的進位是 carry // 2
      # 例如：sum = 2, 2 // 2 = 1 (進位)
      #       sum = 1, 1 // 2 = 0 (不進位)
      carry //= 2

    # 因為是從右到左計算，結果是反的，需要反轉回來
    return "".join(reversed(result))
```

## Python 拔刀術

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