# 000. Problem Name
## Inputs

    nums - Array of integers
    k - Integer

## Outputs

    Rotate array by k steps to the right.

## Constraints

    1 <= nums.length <= 10^5
    -231 <= nums[i] <= 231 - 1
    0 <= k <= 10^5


## Psudo-code

    function rotate(nums) {
        loop k times
            pop element from nums
            add to beginning of nums            
    }

## Code

```js
function rotate(nums: number[], k: number): void {
    for (let i = 0; i < k; i++) {
        nums.unshift(nums.pop())
    } 
}
```

## Submission

    Success
    
    Runtime: 861 ms, faster than 23.96% of TypeScript online submissions for Rotate Array.
    
    Memory Usage: 58.9 MB, less than 67.92% of TypeScript online submissions for Rotate Array.