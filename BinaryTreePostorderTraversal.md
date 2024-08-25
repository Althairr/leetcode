```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def postorderTraversal(self, root):
        """
        :type root: TreeNode
        :rtype: List[int]
        """
        # define result variable to store the traversal
        result = []
        
        # recursive to simulate the post_order
        def post_order(root):
            if root:
                # traverse the left side of the tree
                post_order(root.left)

                # traverse the right side of the tree
                post_order(root.right)

                # after the left and right side have been visited, traverse the current node
                result.append(root.val)
        
        # call the function to start traversing the tree
        post_order(root)

        return result
