```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def mergeTwoLists(self, list1, list2):
        """
        :type list1: Optional[ListNode]
        :type list2: Optional[ListNode]
        :rtype: Optional[ListNode]
        """
        # dummy pointer to serve as the start of the merged lists
        pointer1 = ListNode()

        # add a pointer variable to build the merged list
        curr = pointer1

        # traversing both of the lists until reach the end of one
        while list1 and list2:
            # compare the value of the current nodes of list1 and list2
            if list1.val < list2.val:
                # store/point the value
                curr.next = list1
                # move to the next item/node
                list1 = list1.next
            else:
                # do the same for list2
                curr.next = list2
                list2 = list2.next
            
            # point to the next item/node in the merged list
            curr = curr.next

        # if either of the list is empty, link the curr variable to the remaining lists
        if list1:
            curr.next = list1
        else:
            curr.next = list2

        # return the merged list starting from the node after the dummy pointer
        return pointer1.next
```

## NOTE : in this problem, i can solve this problem because i see a clear explanation in the discussion section.
