---
title: "Grind 75 Python 做題記錄 21. Merge Two Sorted Lists"
date: 2025-10-11T10:14:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 21. Merge Two Sorted Lists

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/merge-two-sorted-lists/description/)

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
        # 建立虛擬頭部
        dummy_head = ListNode()
        # 當前頭部節點
        current_node = dummy_head 
        # 遍歷 list1 與 list2
        while list1 and list2:
            # 假如 list1 較小，將其放入結果串列
            if list1.val < list2.val:
                current_node.next = ListNode(val=list1.val)
                # list1 前進一個
                list1 = list1.next
            # 假如 list2 較小，同上
            else:
                current_node.next = ListNode(val=list2.val)
                list2 = list2.next
            # 將當前節點前推
            current_node = current_node.next
        # 將最後一個節點安上
        current_node.next = list1 or list2
        return dummy_head.next
```