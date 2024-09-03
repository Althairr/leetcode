```python
class Solution(object):
    def getLucky(self, s, k):
        """
        :type s: str
        :type k: int
        :rtype: int
        """

        # convert the characters in the string to their respective positions in the alphabet
        string = ""

        # loop the entire character and convert it alphabetically 
        # add it into the string
        for i in s:
            string += str(ord(i) - ord('a') + 1)

        # perform the transformation k times
        for _ in range(k):
            sum_digit = 0

            # sum all the digits in the current string
            for char in string:
                sum_digit += int(char)

            # convert the sum back to a string for the next iteration
            string = str(sum_digit)

        return int(string)
