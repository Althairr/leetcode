```python
class Solution(object):
    def plusOne(self, digits):
        """
        :type digits: List[int]
        :rtype: List[int]
        """
        # iterate over the list in reverse order (starting from the last digit)
        for i in reversed(range(len(digits))):
            # get the current digit
            n = digits[i]
            
            # if the current digits is 9, change it into 0 (added by 1)
            if n == 9:
                digits[i] = 0
            else :
                # if the current digits is not 9, just add 1 into it and return 
                digits[i] += 1
                return digits

        # if we have looped through all digits and all were 9,
        # we need to add a leading 1 at the beginning (e.g., 999 + 1 = 1000)
        return [1] + digits

```
