```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def addTwoNumbers(self, l1, l2):
        """
        :type l1: ListNode
        :type l2: ListNode
        :rtype: ListNode
        """
        # initialize a dummy node and the result pointer
        dummy = ListNode()

        # pointer to traverse the list and build the result
        result_ptr = dummy

        # initialize total and carry
        total = carry = 0

        # loop until both l1 and l2 are exhausted and there is no carry left
        while l1 or l2 or carry:
            total = carry

            # if still there is an item in l1
            if l1:
                # add the value of the current node of l1 to total
                total += l1.val
                # move to the next node in l1
                l1 = l1.next
            
            # if still there is an item in l2, 
            # works the same like l1
            if l2:
                total += l2.val
                l2 = l2.next

            # the current digit to store in the new node (modulo 10 of total)
            num = total % 10

            # the carry for the next iteration (integer division of total by 10)
            carry = total // 10

            # create a new node with the current digit and link it,
            # then move to the next node
            dummy.next = ListNode(num)
            dummy = dummy.next

        return result_ptr.next
```
