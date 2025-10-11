---
title: "Grind 75 Python 做題記錄 232. Implement Queue using Stacks"
date: 2025-10-11T10:23:44+08:00
draft: false
featured_image: "/code.jpg"
tags: ["leetcode"]
---

# Grind 75 Python 做題記錄 232. Implement Queue using Stacks

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/implement-queue-using-stacks/description/)

```python
class MyQueue:

    def __init__(self):
        self.stack1 = list()
        self.stack2 = list()

    def push(self, x: int) -> None:
        # Push 的時候放入 Stack1
        self.stack1.append(x)

    def pop(self) -> int:
        # Pop 的時候，如果 Stack2 存在元素，先從 Stack2 倒出
        if self.stack2: return self.stack2.pop()
        
        # 如果 Stack2 為空，則將 stack1 倒入 stack2
        while self.stack1:
            self.stack2.append(self.stack1.pop())
        # 回傳 Stack2
        return self.stack2.pop()

    def peek(self) -> int:
        # peek 的時候，如果 Stack2 存在元素，先顯示 Stack2 最後一個
        if self.stack2: return self.stack2[-1]

        # 如果 Stack2 為空，則將 stack1 倒入 stack2
        while self.stack1:
            self.stack2.append(self.stack1.pop())
        # 顯示 Stack2 最後一個
        return self.stack2[-1]

    def empty(self) -> bool:
        if not self.stack1 and not self.stack2:
            return True
        else:
            return False

# Your MyQueue object will be instantiated and called as such:
# obj = MyQueue()
# obj.push(x)
# param_2 = obj.pop()
# param_3 = obj.peek()
# param_4 = obj.empty()
```