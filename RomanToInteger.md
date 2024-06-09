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

## Analysis && Explanation
- `romanToInt` function will accept one parameter `s` which `s` is input from the user (roman numerals). This function will return the roman result. If user input "III", the program will output 3.
- The logic behind this program is when the previous roman is lower than the next roman, it will do subtraction. The program will do addition for the opposite.
- To solve this problem, first i define the dictionary for roman numerals in a variable named `roman_numerals`. Each roman numerals will have its value, for example "I" is 1, "V" is 5, and so on.
- In the for loop algorithm, i use `for roman_char in reversed(s):`. As we can see, i use `reversed(s)` so `roman_char` can iterate over the character of s (although the iteration `roman_char` will output in reversed). 
-  Because i reverse the input that the user give, the logic become `if value < prev_value: result -= value` and will do `result += value` for the opposite.
-  Do not forget set the previous value variable `prev_value = value`.
-  Lastly, it will return the variable `result` that contains the result of the roman numerals to the user.
  
                
