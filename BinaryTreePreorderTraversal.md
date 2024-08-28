```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def preorderTraversal(self, root):
        """
        :type root: TreeNode
        :rtype: List[int]
        """

        # first, define a variable to store the result
        result = []

        # then, recursive to simulate the preorder traversal
        def preorder(root):
            if root:
                # store the root value 
                result.append(root.val)

                # traverse the left-side root
                preorder(root.left)

                # next, traverse the right-side root
                preorder(root.right)
                
        preorder(root)

        return result
```
