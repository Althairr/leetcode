```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def deleteDuplicates(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """

        if not head:
            return None
        
        # initialize a temporary variable to point the linked list
        temp = head

        # while there is still next item in the linked list
        while temp.next:
            # check if the item in the linked list have the same value
            # with the next item 
            if temp.val == temp.next.val:
                # if the duplicate is in the last node
                # (doesn't have next node)
                if not temp.next.next:
                    # delete the node and break the loop
                    temp.next = None
                    break

                # move the pointer to the next node
                # (skip the duplicate node)
                temp.next = temp.next.next
            else:
                # move to the next node
                temp = temp.next

        return head
```
