# 000. Problem Name
## Inputs

    nums - Array of integers

## Outputs

    Element with > n/2 occurences in the array


## Constraints

    n == nums.length
    1 <= n <= 5 * 10^4
    -10^9 <= nums[i] <= 10^9


## Psudo-code

    function majorityElement(nums) {
        sort nums in ascending order
        return nums[Math.floor(nums.length/2)]
    }

## Code

```js
function majorityElement(nums: number[]): number {
    nums.sort((a, b) => a - b)
    return nums[Math.floor(nums.length / 2)]
}
```

## Submission

    Success
    
    Runtime: 63 ms, faster than 64.82% of TypeScript online submissions for Majority Element.
    
    Memory Usage: 53.8 MB, less than 52.23% of TypeScript online submissions for Majority Element.