```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def maxDepth(self, root):
        """
        :type root: TreeNode
        :rtype: int
        """
        # if the root is empty, just return 0 
        if not root:
            return 0
        
        # traverse the left side tree and right side tree
        left_depth = self.maxDepth(root.left)
        right_depth = self.maxDepth(root.right)

        # return the max level of either node and add 1 into it (because root considered at level 1)
        return max(left_depth, right_depth) + 1
```
