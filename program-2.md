# Program 2: Maximum Stock Profit

DefineWrite a program that finds the best days to buy and sell stocks to maximize profit, given an array of stock prices. Return the maximum profit that can be made. If no profit can be made, return -1.

### samples

<table>
<tr>
<th> Input </th>
<th> Output </th>
</tr>
<tr>
<td>
[100,180,260,310,40,535,695]
</td>
<td>
 Buy on day 5 at price 40 <br/>
 Sell on day 7 at price 695 <br/>
 Max profit: 655 
 </td>
 </tr>
 </table>

### Tasks
- Develop program using your choice of programming language
- Create test script covering all scenarios (min 5 test cases)
- Add comments/documentation to the code


 // DefineWrite a program that finds the best days to buy and sell stocks to maximize profit, given an array of stock prices. Return the maximum profit that can be made. If no profit can be made, return -1.
 
def max_profit(prices):
    if not prices:
        return -1

    min_price = prices[0]
    max_profit = 0

    for price in prices:
        # Update the minimum buy price
        min_price = min(min_price, price)
        # Calculate the potential profit if sold today
        potential_profit = price - min_price
        # Update the maximum profit if the potential profit is higher
        max_profit = max(max_profit, potential_profit)

    if max_profit == 0:
        return -1

    return max_profit

# Example usage:
stock_prices = [7, 1, 5, 3, 6, 4]
result = max_profit(stock_prices)
print(result)  # Output should be 5 (buy on day 2 at price 1 and sell on day 5 at price 6)
