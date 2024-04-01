# 209. Minimum Size Subarray Sum
## Inputs

    nums - Array of positive integers
    target - Positive integer

## Outputs

    Minimal length of a subarray whose sum is greater than or equal to target, or 0 if no sum exists.

    Subarray - contiguous part of nums

## Constraints

    1 <= target <= 10^9
    1 <= nums.length <= 10^5
    1 <= nums[i] <= 10^4

## Psudo-code

    function minSubArrayLen(target, nums) {
        n = nums.length
        smallestLength = max_int
        windowSum = 0

        windowStart = 0
        for windowEnd = 0; windowEnd < n; windowEnd++
            windowSum += nums[windowEnd]

            while windowSum >= target
                smallestLength = windowEnd - windowStart + 1
                windowSum -= nums[windowStart]
                windowStart++

        return smallestLength === max_int ? 0 : smallestLength
    }

## Code

```js
function minSubArrayLen(target: number, nums: number[]): number {
    const n = nums.length
    let smallestLength = Number.MAX_SAFE_INTEGER
    let windowSum = 0
    
    let windowStart = 0
    for (let windowEnd = 0; windowEnd < n; windowEnd++) {
        windowSum += nums[windowEnd]

        while(windowSum >= target) {
            smallestLength = Math.min(windowEnd - windowStart + 1, smallestLength)
            windowSum -= nums[windowStart]
            windowStart++
        }
    }

    return smallestLength === Number.MAX_SAFE_INTEGER ? 0 : smallestLength 
}
```

## Submission

    Success

    Runtime: 83 ms, faster than 9.57% of TypeScript online submissions for Minimum Size Subarray Sum.

    Memory Usage: 55.4 MB, less than 52.78% of TypeScript online submissions for Minimum Size Subarray Sum.