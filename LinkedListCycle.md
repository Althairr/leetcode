```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def hasCycle(self, head):
        """
        :type head: ListNode
        :rtype: bool
        """
        # initialize two pointer to become the slow pointer and the fast pointer
        slow = head # traverse one node at a time
        fast = head # traverse two node at a time

        # loop through the lists
        while fast and fast.next:
            # traversing..
            slow = slow.next
            fast = fast.next.next

            # if they met, then there is a cycle on the linked list
            if slow is fast:
                return True
        
        # if not, then there is no cycle
        return False
