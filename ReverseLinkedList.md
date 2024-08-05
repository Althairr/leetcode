```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def reverseList(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """

        result = []
        current = head

        while current is not None:
            result.append(current.val)
            current = current.next
        
        # reverse the list
        result.reverse()

        if not result:
            return None

        # now change back into linked list
        # create the head of the linked list
        head = ListNode(result[0])
        current = head

        # iterate over the remaining elements and create nodes
        for value in result[1:]:
            current.next = ListNode(value)
            current = current.next

        return head
```
