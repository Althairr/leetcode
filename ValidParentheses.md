```python
  class Solution(object):
    def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        # use stack
        # initialize stack
        stack = []

        # loops through the input
        for char in s:
            # if the parentheses is the opening and meet the requirement
            if char in ["(", "[", "{"]:
                # add it into the stack
                stack.append(char)
            else:
                # if stack still empty, the first input must be the closing parentheses
                if not stack:
                    return False
                
                # mark the popped char with variable to check the closing parentheses
                marked_char = stack.pop()

                # ensure that the marked char with each opening parentheses have the matching closing parentheses
                if marked_char == "(":
                    if char != ")":
                        return False
                if marked_char == "[":
                    if char != "]":
                        return False
                if marked_char == "{":
                    if char != "}":
                        return False
        
        # if stack still not empty, return false
        if stack:
            return False
        
        # stack is empty, successfully popped all char (matching)
        return True
                        
                
```
