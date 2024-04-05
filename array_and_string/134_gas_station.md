# 134. Gas Station
## Inputs

    gas - Array of integers, represents refill val at each station

    cost - Array of integers, represents usage val to get to next station

## Outputs

    Index of starting station if a clockwise round trip can be made, else -1.

## Constraints

    n == gas.length == cost.length
    1 <= n <= 10^5
    0 <= gas[i], cost[i] <= 10^4

## Psudo-code

    function canCompleteCircuit(gas, cost) {
        n = gas.length
        // Create totalNetGas to track net gass of full cuircuit
        // Create tank to keep track of positive net cost moves
        totalNetGas = 0
        tank = 0
        start = 0

        // Walk forward through gas and cost
        // Set tank and totalNetGas to cumulatively add current net gas
        // If tank becomes negative reset it and set start to next index
        for let i = 0; i < n; i++
            tank += gas[i] + cost[i]
            totalNetGas += gas[i] + cost[i]

            if (tank < 0) 
                tank = 0
                start = i + 1
        
        return totalNetGas >= 0 ? start : -1
    }

## Code

```js
function canCompleteCircuit(gas: number[], cost: number[]): number {
    const n = gas.length
    
    let totalNetGas = 0
    let tank = 0
    let start = 0

    for (let i = 0; i < n; i++) {
        tank += gas[i] - cost[i]
        totalNetGas += gas[i] - cost[i]
        if (tank < 0) {
            tank = 0
            start = i + 1
        }
    }

    return totalNetGas >= 0 ? start : -1
    
}
```

## Submission

    Success

    Runtime: 77 ms, faster than 76.24% of TypeScript online submissions for Gas Station.

    Memory Usage: 60.7 MB, less than 95.21% of TypeScript online submissions for Gas Station.