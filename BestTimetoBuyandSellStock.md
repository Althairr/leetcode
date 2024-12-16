```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        # The buying price set to the first item on the list
        buy_prices = prices[0]

        # The profit initialized at 0 because on day one you can't get the profit
        profit = 0

        # loop through the lists to find the maximum profit
        for p in prices[1:]:
            # Check if the first day buying price is more expensive than 
            # the next day 
            if buy_prices > p:
                # Buy with the next day price
                buy_prices = p
            
            # Update the profit we get
            profit = max(profit, p-buy_prices)
        
        # Return the max profit we can get by the list of prices
        return profit
            

        
