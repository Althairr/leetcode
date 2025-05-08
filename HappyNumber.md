```python
class Solution:
    def isHappy(self, n: int) -> bool:
        # initialize set to keep the numbers
        num_seen = set()

        while True:
            # variable to track the result, set to 0 for new iteration
            total = 0

            # if the n is 1, automatically return True
            if n == 1:
                return True
            
            # ensure that the number is not has been seen (looping over and over)
            if n in num_seen:
                return False

            # add n to seen (ensure no looping endlessly)
            num_seen.add(n)

            # looping each number
            for digits in str(n):
                total += int(digits) ** 2

            # assign n to its new value
            n = total
```
