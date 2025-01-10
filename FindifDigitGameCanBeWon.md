```python
class Solution:
    def canAliceWin(self, nums: List[int]) -> bool:
        # declare variable
        single_sum = 0 # for single digits
        double_sum = 0 # for double digits

        for num in nums:
            if (num > 9):
                double_sum += num
            else:
                single_sum += num
        
        return single_sum != double_sum
