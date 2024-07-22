```python
class Solution(object):
    def intToRoman(self, num):
        """
        :type num: int
        :rtype: str
        """

        # initialize variable and symbols
        symbol =  ["M", "CM", "D", "CD", "C", "XC", "L", "XL", "X", "IX", "V", "IV", "I"]
        value = [1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1]
        roman_numeral = "" # to store the answer

        # initialize variable to iterate through the list.
        # the purpose is so that we will start iterate 
        # from the largest value and work down to the smallest
        i = 0 

        # ensure that the num greater than 0 (still can be subtracted)
        while num > 0:
            # determine how many times the current value can fit into num
            for _ in range(num // value[i]):
                # append the corresponding roman numeral symbol to the result
                roman_numeral += symbol[i]
                # subtract the value from num
                num -= value[i]
            # move to the next smaller value
            i += 1

        # return the result    
        return roman_numeral
```
