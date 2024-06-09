``` python
class Solution(object):
    def romanToInt(self, s):
        """
        :type s: str
        :rtype: int
        """

        # define the roman numerals
        roman_numerals = {
        "I": 1,
        "V": 5,
        "X": 10,
        "L": 50,
        "C": 100,
        "D": 500,
        "M": 1000
        }

        # prepare the variable
        result = 0
        prev_value = 0

        # get each roman input reversed
        for roman_char in reversed(s):
            # set value based on the dictionary
            value = roman_numerals[roman_char]

            # check if the value is greater (or not) when compared to prev value
            if value < prev_value: # if value lower than the previous value
                result -= value
            else: 
                # add value
                result += value

                # set the previous value
                prev_value = value
            
        return result
```
