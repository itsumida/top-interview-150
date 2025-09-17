# Question
You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

# Approach
Track the lowest price so far, and at each step calculate the profit if you sold today, keeping the maximum.

# Solutioin
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        profit = 0
        min_cost = prices[0]

        for price in prices[1:]:
            profit = max(profit, price-min_cost)
            min_cost = min(price, min_cost)

        return profit
