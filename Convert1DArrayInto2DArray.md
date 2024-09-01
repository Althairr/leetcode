```python
class Solution(object):
    def construct2DArray(original, m, n):
    # Check if the input list has the correct number of elements
    if len(original) != m * n:
        return []  # Return an empty list if the dimensions don't match
    
    # Create a 2D list (matrix) with m rows and n columns, filled with zeros
    ans = [[0 for _ in range(n)] for _ in range(m)]
    
    # Initialize a counter to keep track of position in the original list
    k = 0
    
    # Iterate through each position in the 2D array
    for i in range(m):  # For each row
        for j in range(n):  # For each column in the current row
            ans[i][j] = original[k]  # Assign the value from original to the current position
            k += 1  # Move to the next element in the original list
    
    # Return the constructed 2D array
    return ans
