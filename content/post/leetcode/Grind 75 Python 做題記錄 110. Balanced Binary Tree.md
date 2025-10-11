---
title: "Grind 75 Python 做題記錄 110. Balanced Binary Tree"
date: 2025-10-11T10:22:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 110. Balanced Binary Tree

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/balanced-binary-tree/description/)

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isBalanced(self, root: Optional[TreeNode]) -> bool:
        # 深度優先搜索函數
        def dfs(root: Optional[TreeNode]):
            # 如果觸底，回傳0
            if not root: return 0

            # 計算左右側深度
            left_hight = dfs(root.left)
            right_hight = dfs(root.right)

            # 檢查是否左右側有-1
            if left_hight == -1 or right_hight == -1: return -1 
            # 左右側子樹差異為-1，則回傳 -1
            if abs(left_hight - right_hight) > 1: return -1

            # 回傳當前高度
            return max(left_hight, right_hight) + 1

        # 檢查是否回傳 -1
        return not (dfs(root) == -1)
```