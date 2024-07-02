```python
class Solution(object):
    def hammingWeight(self, n):
        """
        :type n: int
        :rtype: int
        """
        # initialize variable to count the 1 bits
        count_1bits = 0

        # loop until n is zero
        while n:
            # increment count by the result of the operation AND bitwise with 1
            count_1bits += n & 1
            # shift n one bit to the right
            n = n >> 1

        # return
        return count_1bits
```
