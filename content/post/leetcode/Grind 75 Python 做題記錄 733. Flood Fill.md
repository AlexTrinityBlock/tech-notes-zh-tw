---
title: "Grind 75 Python 做題記錄 733. Flood Fill"
date: 2025-10-11T10:20:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 733. Flood Fill

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/flood-fill/description/)

```python
class Solution:
    def floodFill(self, image: List[List[int]], sr: int, sc: int, color: int) -> List[List[int]]:
        # 取得寬度與高度
        row_len:int = len(image)
        col_len:int = len(image[0])
        # 取得起點顏色
        origin_color = image[sr][sc]
        # 如果起點顏色為目標顏色，直接回傳
        if origin_color == color: return image

        # 深度優先遞迴函數
        def dfs(sr,sc):
            # 超出圖片外圍，則終止
            if sr < 0 or sr >= row_len: return
            if sc < 0 or sc >= col_len: return
            # 如果當前顏色不是採樣顏色，則終止
            if image[sr][sc] != origin_color: return

            # 著色
            image[sr][sc] = color

            # 著色其他地方
            dfs(sr + 1,sc)
            dfs(sr - 1,sc)
            dfs(sr,sc + 1)
            dfs(sr,sc - 1)

        # 開始著色
        dfs(sr, sc)
        # 回傳圖片
        return image
```