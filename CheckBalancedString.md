```python
class Solution:
    def isBalanced(self, num: str) -> bool:
        # Initialize variable for calculating
        odd_nums = 0
        even_nums = 0

        # Loop through the list of num
        for i in range(len(num)):
            # If the number mod by 2 is 0, assign to even numbers. 
            if i % 2 == 0:
                even_nums += int(num[i])
            else :
                # Else its odd numbers
                odd_nums += int(num[i])
        
        # Check whether the sum of even and odd are balanced and return it
        return odd_nums == even_nums
