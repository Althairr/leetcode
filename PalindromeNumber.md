## Palindrome Algorithm

## Description
This Python class `Solution`  implements the `Palindrome` algorithm, which is used to check whether input from the user is palindrome or not.

## Method
The `Palindrome` method takes one parameter:
- `x`: an integer representing the input from the user.

It returns a boolean. If the input is considered to be polindrome, it will return True. Return False for the opposite.

```python
class Solution(object):
    def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        
        # convert the input into lists
        x_lists = str(x)

        # track the items on the lists
        n = len(x_lists)

        # check the last items if its match or not to the first items
        for i in range(n // 2):
            if x_lists[i] != x_lists[n - i - 1]: # check the last items  of the lists
                return False
        
        # else return true (polindrome)
        return True
```
 ## Analysis & Explanation
 - First, i use `x_lists` as a variable to convert the input into a string. This string later will be viewed as lists.
 - Then, i use `n` as a variable to track the length of the user input or can be interpreted as the length of the variable `x_lists`. This variable later will be used for optimize the loop.
 - `for i in range(n // 2)` make my loop do less work (work more efficient). Let's say that the input has length of 3. Later the loop will divide the length (`n`) by 2 so that it will ignore the middle number. Because of that, `i` will have a value range of 0 until i < 1 (because `//` will make 3 divided by 2 output 1,5 and the output will be rounded to its floor (only 1)). So the range only `i = 0`.
 - (continued from before) Then, the `x_lists[i] != x_lists[n - i - 1]` will become `x_lists[0] != x_lists[n-1]`. `x_lists[0]` will access the first value of the string (or list) and `x_lists[n-1]` will access the last value of the list.
 - If the if rule is true, that means the first and last value not have the same value (not polindrome). If the of rule is false, then the program will break from the if rule and will return true.
