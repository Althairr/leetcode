```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def removeElements(self, head, val):
        """
        :type head: ListNode
        :type val: int
        :rtype: ListNode
        """

        # create node dummy, later will be used
        dummy = ListNode(next = head)   

        # add a temp variable to point the head
        temp = head

        # add a variable to point the current node
        current = dummy

        # traverse the list 
        while temp is not None:
            # while the node is stil not the value
            if temp.val != val:
                # set the current node to the next node
                current.next = temp  

                # move the current node
                current = current.next
            
            # move the temp (while traversing) into the next node
            temp = temp.next

        # set the node that match the value to None (delete)
        current.next = None

        # return the list
        return dummy.next
 ```
