# 135. Candy
## Inputs

    ratings - Array of integers

## Outputs

    Minimum number of candies, such that:
        1. Each child must have at least one candy.
        2. Children with a higher rating get more candies than their neighbors.


## Constraints

    n == ratings.length
    1 <= n <= 2 * 10^4
    0 <= ratings[i] <= 2 * 10^4

## Psudo-code

    function candy(ratings) {
        // Create an array candies to keep track of candies per child
        // Create candyCount to keep track of total candies awarded

        n = ratings.length
        candies = new Array(n).fill(1)
        candyCount = n

        // Walk forward and backward through ratings
        for i = 1; i < n; i++
            // If current rating greater than previous rating and current candies not greater than previous candies
            // Add candies such that current candies = previous candies + 1
            // Add diff between old current and new current to candyCount
            if ratings[i] > ratings[i - 1]
                if candies[i] <= candies[i - 1]
                    diff = candies[i - 1] + 1 - candies[i]
                    candies[i] += diff
                    candyCount += diff
            if ratings[n - 1 - i] > ratings[n - i]
                if candies[n - 1 - i] <= candies[n - i]
                    diff = candies[n - i] + 1 - candies[n - 1 - i]
                    candies[n - 1 - i] += diff
                    candyCount += diff
        
        return candyCount
    }

## Code

```js
function candy(ratings: number[]): number {
    const n = ratings.length
    const candies = new Array(n).fill(1)
    let candyCount = n

    for (let i = 1; i < n; i++) {
        if (ratings[i] > ratings[i - 1]) {
            if (candies[i] <= candies[i - 1]) {
                const diff = candies[i - 1] + 1 - candies[i]
                candies[i] += diff
                candyCount += diff
            }
        }
        if (ratings[n - 1 -i] > ratings[n - i]) {
            if (candies[n - 1 -i] <= candies[n - i]) {
                const diff = candies[n - i] + 1 - candies[n - 1 - i]
                candies[n - 1 -i] += diff
                candyCount += diff
            }
        }
    }

    return candyCount
}
```

## Submission

    Success

    Runtime: 49 ms, faster than 100.00% of TypeScript online submissions for Candy.

    Memory Usage: 53.3 MB, less than 95.50% of TypeScript online submissions for Candy.