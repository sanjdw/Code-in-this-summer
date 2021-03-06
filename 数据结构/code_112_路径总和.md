给定一个二叉树和一个目标和，判断该树中是否存在根节点到叶子节点的路径，这条路径上所有节点值相加等于目标和。

**说明**: 叶子节点是指没有子节点的节点。

**示例:**
给定如下二叉树，以及目标和`sum = 22`，
```
              5
             / \
            4   8
           /   / \
          11  13  4
         /  \      \
        7    2      1
```
返回`true`, 因为存在目标和为`22`的根节点到叶子节点的路径 `5->4->11->2`。

### 递归
```js
function hasPathSum (root, sum) {
  if (!root) return false
  if (root.left || root.right) {
    return hasPathSum(root.left, sum - root.val) || hasPathSum(root.right, sum - root.val)
  } else {
    return root.val === sum
  }
}
```

时间复杂度`O(n)`，`n`是树节点数，因为要对每个节点访问一次。
空间复杂度`O(H)`，`H`是树的高度。

### 广度优先搜索
[广度优先搜索](https://leetcode-cn.com/problems/path-sum/solution/lu-jing-zong-he-by-leetcode-solution/)

```js
// todo
```