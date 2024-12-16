```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def sortedArrayToBST(self, nums: List[int]) -> Optional[TreeNode]:
        # Ensure that the array is not empty
        if not nums:
            return None
        
        # Find the middle value to be the root
        middle_value = len(nums) // 2
        root = TreeNode(nums[middle_value])

        # Traverse the tree
        root.left = self.sortedArrayToBST(nums[:middle_value])
        root.right = self.sortedArrayToBST(nums[middle_value+1:])

        return root       
