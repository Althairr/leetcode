```python
class Solution(object):
    def isUgly(self, n):
        """
        :type n: int
        :rtype: bool
        """
        # must be positive
        if n <= 0:
            return False  
        
        # assign to a new variable
        num = n  
                
        # check whether can it divide by 2, 3, or 5 (ugly number) or prime number
        for num_prime in [2, 3, 5]:
            while num % num_prime == 0:
                num /= num_prime
        
        return num == 1
```
