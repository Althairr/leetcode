```python
class Solution(object):
    def mySqrt(self, x):
        """
        :type x: int
        :rtype: int
        """
        # using binary search 
        # initialize the left and right
        left = 0
        right = x

        # do the binary search
        while left <= right:
            # initialize the middle 
            mid = (left + right) // 2

            # check whether the (mid * mid) is less than the x or not
            if mid * mid < x:
                # make 'left' point to the 'mid + 1' 
                left = mid + 1
            # check whether the (mid * mid) is greater than the x or not
            # to find the half of the left
            elif mid * mid > x:
                # make 'right' point to the 'mid - 1'
                right = mid - 1
            else:
                # return the correct answer
                return mid

        # if the binary search did not find 'x' then it must be the x itself
        return right
```
