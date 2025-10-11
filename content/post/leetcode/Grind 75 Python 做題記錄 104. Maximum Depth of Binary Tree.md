---
title: "Grind 75 Python 做題記錄 104. Maximum Depth of Binary Tree"
date: 2025-10-11T10:02:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 104. Maximum Depth of Binary Tree

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/maximum-depth-of-binary-tree/description/)

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        # 觸底返 0 
        if not root: return 0
        # 取左右深度最大值
        max_depth_until_now = max(self.maxDepth(root.left),self.maxDepth(root.right))
        # 回傳值加上當前 1 個深度
        return max_depth_until_now + 1
```