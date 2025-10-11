---
title: "Grind 75 Python 做題記錄 235. Lowest Common Ancestor of a Binary Search Tree"
date: 2025-10-11T10:21:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 235. Lowest Common Ancestor of a Binary Search Tree

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/description/)

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def lowestCommonAncestor(self, root: 'TreeNode', p: 'TreeNode', q: 'TreeNode') -> 'TreeNode':
        # 如果走到底仍沒有找到則終止
        if not root or not p or not q: return
        # 循環條件
        while root:
            # 如果 p 與 q 都小於 root
            if p.val < root.val and q.val < root.val:
                root = root.left
            # 如果 p 與 q 都大於 root
            elif p.val > root.val and q.val > root.val:
                root = root.right
            # 如果不符合上述條件即是找到
            else:
                return root
```