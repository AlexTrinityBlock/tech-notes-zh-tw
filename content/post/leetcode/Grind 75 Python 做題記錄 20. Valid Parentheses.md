---
title: "Grind 75 Python 做題記錄 20. Valid Parentheses"
date: 2025-10-11T10:12:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 20. Valid Parentheses

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/valid-parentheses/description/)

```python
class Solution:
  def isValid(self, s: str) -> bool:
    # 若為空字串直接返回
    if len(s) == 0: return True
    # 建立括弧對的紀錄
    pari_dict:dict = {
      ")":"(",
      "}":"{",
      "]":"["
    }
    # 建立 stack
    stack = list()
    # 遍歷字串
    for char in s:
      # 假如是右括號
      if char in pari_dict:
        # 若字串尚未結束，但 pop 為 0 回傳 False
        if len(stack) == 0: return False
        # 確認是否有對應左括號在 stack 中，若無法對上，就回傳 False 
        if stack.pop() != pari_dict[char]: return False
      # 左括號的情況
      else:
        # 放入 stack
        stack.append(char)
    # 假如最後 Stack 為空，則回傳 True
    if len(stack) == 0:
      return True
    else:
      return False
```