```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def isSameTree(self, p, q):
        """
        :type p: TreeNode
        :type q: TreeNode
        :rtype: bool
        """
        # ensure that variable p and q have value, if both doesn't have value
        # just return True
        if not p and not q:
            return True

        # now check if p and q is not none, and they have the same root value
        if p and q and p.val == q.val:
            # recurively call the function to ensure that the next node is the same value too
            return self.isSameTree(p.left, q.left) and self.isSameTree(p.right, q.right)
        
        # if neither condition is met, return False
        return False
```
