---
title: "Grind 75 Python 做題記錄 383. Ransom Note"
date: 2025-10-11T10:05:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 383. Ransom Note

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/ransom-note/description/)

## 答題

```python
class Solution:
    def canConstruct(self, ransomNote: str, magazine: str) -> bool:
        # 將重複字串過濾，變成一個不重複list
        r_list = list(set(ransomNote))
        # 遍歷 List
        for i in r_list:
            # 檢查每個字字數，ransomNote 中某字數不可大於 magazine
            if ransomNote.count(i) > magazine.count(i): return False
        return True  
```