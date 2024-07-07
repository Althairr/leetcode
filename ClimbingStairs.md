```python
class Solution(object):
    def climbStairs(self, n):
        """
        :type n: int
        :rtype: int
        """
        # we can't use recursive because of runtime too slow, except we add memoisation to it
        # if the stairs just have 0 or 1 step, just return 1
        if n == 0 or n == 1:
            return 1

        # 'a' is a way to reach step 0, 'b' for step 1
        a, b = 1, 1

        # start counting for the step 2
        for i in range(2, n+1):
            # update 'a' so have the result of 'b', and 'b' become 'a + b'
            a, b = b, a + b 
        
        # now 'b' is the number of ways to reach step n
        return b
```
