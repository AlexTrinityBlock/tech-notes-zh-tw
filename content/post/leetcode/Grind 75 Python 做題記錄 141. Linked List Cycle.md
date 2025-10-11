---
title: "Grind 75 Python 做題記錄 141. Linked List Cycle"
date: 2025-10-11T10:22:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 141. Linked List Cycle

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/linked-list-cycle/description/)

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        # 快慢指針
        fast = slow = head
        # 快針未觸底
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
            if slow == fast: return True
        # 見底
        return False
```