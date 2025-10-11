---
title: "Grind 75 Python 做題記錄 543. Diameter of Binary Tree"
date: 2025-10-11T10:03:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 543. Diameter of Binary Tree

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/diameter-of-binary-tree/description/)

## 答題

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def diameterOfBinaryTree(self, root: Optional[TreeNode]) -> int:
        # 儲存當前最大寬度
        self.max_diameter = 0
        # 深度搜索函數
        def depth(root):
            # 觸底返 0
            if not root: return 0
            # 計算左右深度
            left_depth = depth(root.left)
            right_depth = depth(root.right)
            # 更新最大寬度
            self.max_diameter = max(self.max_diameter, left_depth + right_depth)
            # 回傳深度加上當前多1的深度
            return max(left_depth, right_depth) + 1
        # 啟動函數
        depth(root)
        # 回傳最大寬度
        return self.max_diameter
```