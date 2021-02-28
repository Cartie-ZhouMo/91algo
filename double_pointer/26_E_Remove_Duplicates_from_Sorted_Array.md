### 思路

- 用一个读指针，一个写指针遍历数组。
- 遇到重复的元素 `读指针` 就继续前移。
- 遇到不同的元素 `写指针` 就前移一步，写入那个元素。

![26](https://github.com/Cartie-ZhouMo/91algo/blob/master/fig/26.png)

### 代码

```python
class Solution(object):
    def removeDuplicates(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        if not nums: return 0

        l, r = 0, 0
        while r < len(nums):
            if nums[l] != nums[r]:
                l += 1
                nums[l] = nums[r]
            r += 1
        return l + 1
```



**复杂度分析**

时间复杂度：$O(N)$

空间复杂度：$O(1)$
