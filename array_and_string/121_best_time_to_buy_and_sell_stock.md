# 121. Best Time to Buy and Sell Stock
## Inputs

    prices - Array of integers

## Outputs

    Maximum positive difference between any two elements, else 0 - integer

## Constraints

    1 buy and 1 sell
    1 <= prices.length <= 10^5
    0 <= prices[i] <= 10^4

## Psudo-code

    function maxProfit(prices) {
        profit = 0
        buy = prices[0]

        // Create pointer i to iterate through prices
        for i = 1; i < prices length; i++
            If prices[i] < buy
                buy = prices[i] and continue
            If prices[i] > buy and prices[i] - buy > profit
                profit = prices[i] - buy

        return profit

    }

## Code

```js
function maxProfit(prices: number[]): number {
    let profit = 0
    let buy = prices[0]

    for (let i = 1; i < prices.length; i++) {
        if (prices[i] < buy) {
            buy = prices[i]
            continue
        }
        if (prices[i] > buy && prices[i] - buy > profit) {
            profit = prices[i] - buy
        }
    }

    return profit
}
```

## Submission

    Success

    Runtime: 83 ms, faster than 40.13% of TypeScript online submissions for Best Time to Buy and Sell Stock.

    Memory Usage: 59.6 MB, less than 59.55% of TypeScript online submissions for Best Time to Buy and Sell Stock.