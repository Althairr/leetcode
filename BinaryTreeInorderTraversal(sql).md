```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def inorderTraversal(self, root):
        """
        :type root: TreeNode
        :rtype: List[int]
        """
        
        # initialize the varuiable to store the result
        result = []

        # nested function
        def inorder_trav(root):
            # if root is None, return (end of recursion)
            if not root:
                return
            
            # traverse the left subtree recursively
            inorder_trav(root.left)
            
            # append current node's value to result list
            result.append(root.val)
            
            # traverse right subtree recursively
            inorder_trav(root.right)
        
        # start inorder traversal from the root of the tree
        inorder_trav(root)
        
        # return the final result list containing inorder traversal of the tree
        return result
```
