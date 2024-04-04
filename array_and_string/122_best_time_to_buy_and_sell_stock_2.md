# 122. Best Time to Buy and Sell Stock II
## Inputs

    prices - Array of integers

## Outputs

    Maximum profit - integer

## Constraints

    Can only hold 1 stock at a time
    At most 1 buy and 1 sell per day
    1 <= prices.length <= 3 * 10^4
    0 <= prices[i] <= 10^4

## Psudo-code

    function maxProfit(prices) {
        profit = 0

        // Boundary condition where profit is impossible
        if prices length < 2 return 0

        // Iterate through prices
        for i = 1; i < prices.length; i++
            // buy the day before the price increases
            // sell the day before the price drops
            // difference added to profit
            if prices[i] > prices[i - 1]
                profit += prices[i] - prices[i - 1]

        return profit


    }

## Code

```js
function maxProfit(prices: number[]): number {
    let profit = 0
    const n = prices.length

    if (n < 2) return 0

    for (let i = 1; i < n; i ++) {
        if (prices[i] > prices[i - 1]) {
            profit += prices[i] - prices[i - 1]
        }
    }

    return profit
}
```

## Submission

    Success

    Runtime: 58 ms, faster than 69.34% of TypeScript online submissions for Best Time to Buy and Sell Stock II.

    Memory Usage: 51.9 MB, less than 39.96% of TypeScript online submissions for Best Time to Buy and Sell Stock II.