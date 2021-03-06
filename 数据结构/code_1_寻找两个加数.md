给定一个整数数组`nums`和一个目标值`target`，请你在该数组中找出和为目标值的那两个整数，并返回他们的数组下标。

你可以假设每种输入只会对应一个答案。但是，数组中同一个元素不能使用两遍。

**示例:**
```
给定 nums = [2, 7, 11, 15], target = 9

因为 nums[0] + nums[1] = 2 + 7 = 9
所以返回 [0, 1]
```

### 暴力求解
直观可以想到的暴力方法：
```js
function find_index (nums, target) {
  for(let i = 0, len = nums.length; i < len; i++) {
    for (let j = i + 1; j < len; j++) {
      if(nums[i] + nums[j] === target){
        return [i, j]
      }
    }
  }
  return -1
}
```

### 哈希表
利用哈希表，节省一层遍历：
```js
function find_index_new (nums, target) {
  const result = []
  const map = {}
  let temp
  for (let i = 0, len = nums.length; i < len; i++) {
    temp = target - nums[i]
    if (map[temp] !== undefined) {
      result[0] = map[temp]
      result[1] = i
      return result
    }
    map[nums[i]] = i
  }
  return -1
}
```

时间复杂度`O(n^2)` ---> `O(n)`