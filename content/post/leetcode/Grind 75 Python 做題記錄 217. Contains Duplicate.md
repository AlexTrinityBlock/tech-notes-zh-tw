# Grind 75 Python 做題記錄 217. Contains Duplicate

[Grind 75 連結](https://www.techinterviewhandbook.org/grind75/)

[Leetcode 題目連結](https://leetcode.com/problems/contains-duplicate/)

## 答題

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        # Set 長度與字串長度不同，代表有重複
        return len(set(nums)) != len(nums)
```