```python
class Solution:
    def finalPrices(self, prices: List[int]) -> List[int]:
        # Loop through all of list of prices
        for i in range(len(prices)):
            # Loop through the next prices
            for j in range(i+1, len(prices)):
                # Check if the next price is greater than the current price
                if prices[j] <= prices[i]:
                    # If it is, then give discount to the current price 
                    # reduced by the next price
                    prices[i] -= prices[j]
                    break

        return prices

        
