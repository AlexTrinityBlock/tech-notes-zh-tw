---
title: "Grind 75 Python 做題記錄 876. Middle of the Linked List"
date: 2025-10-11T10:01:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 876. Middle of the Linked List

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/middle-of-the-linked-list/description/)

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        # 建立快慢針
        fast = slow = head
        # 快針遍歷，快針結束，慢針過半
        while fast and fast.next:
            # 慢針進1
            slow = slow.next
            # 快針進2
            fast = fast.next.next
        # 回傳過半慢針
        return slow
```