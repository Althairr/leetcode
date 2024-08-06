```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def hasPathSum(self, root, targetSum):
        """
        :type root: TreeNode
        :type targetSum: int
        :rtype: bool
        """
        # backtracking!!!

        # ensure that root is exists, if not just return false
        if not root:
            return False

        # if its already leaf node, check whether this node value 
        # have a same value with targetSum
        if not root.left and not root.right:
            return targetSum == root.val

        # simulate the backtrack recursively
        if self.hasPathSum(root.left, targetSum - root.val) or self.hasPathSum(root.right, targetSum - root.val):
            return True
        
        return False
```
