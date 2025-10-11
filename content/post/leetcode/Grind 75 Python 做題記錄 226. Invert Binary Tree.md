---
title: "Grind 75 Python 做題記錄 226. Invert Binary Tree"
date: 2025-10-11T10:17:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 226. Invert Binary Tree

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/invert-binary-tree/)

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:
        # 假如傳入節點為空，終止遞迴
        if not root: return
        # 遞迴調換左右節點
        temp_left: TreeNode = self.invertTree(root.right)
        temp_right: TreeNode = self.invertTree(root.left)
        # 將調換後的左右節點安裝回樹上
        root.left = temp_left 
        root.right = temp_right 
        return root
```