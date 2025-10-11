---
title: "Grind 75 Python 做題記錄 206. Reverse Linked List"
date: 2025-10-11T10:08:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 206. Reverse Linked List

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/reverse-linked-list/description/)

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        # 前一個指標
        prev = None
        # 當前指標
        curr = head
        # 遍歷串列
        while curr:
            # 暫存下個指標
            temp_next = curr.next
            # 將當前指標指向反轉
            curr.next = prev
            # 將前個指標指向當前指標
            prev = curr
            # 將當前指標向後移動
            curr = temp_next
        # 回傳移動到新頭部的 prev
        return prev
```