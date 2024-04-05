# 238. Product of Array Except Self
## Inputs

    nums - Array of integers

## Outputs

    answer - Array of integers
    
    answer[i] equals the product of all elements of nums excluding nums[i]

## Constraints

    2 <= nums.length <= 10^5
    -30 <= nums[i] <= 30
    The product of any prefix or suffix of nums is guaranteed to fit in a 32-bit integer.
    O(n) run time, without using the division operation.

## Psudo-code

    function productExceptSelf(nums) {
        // Create curPre = nums[0] to keep track of pre-product
        // Create curPost = nums[lenth - 1] to keep track of post-product
        // Create new Array(nums length).fill(1) answer

        // Walk forward through array starting at i = 1
        let i = 1; i < nums length; i ++
            answer[i] *= curPre
            answer[nums length - 1 - i] *= curPost
            curPre *= nums[i]
            curPost *= nums[nums length - 1 - i]
    
        return answer
    }

## Code

```js
function productExceptSelf(nums: number[]): number[] {
    const n = nums.length
    const answer = new Array(n).fill(1)

    let curPre = nums[0]
    let curPost = nums[n - 1]

    for (let i = 1; i < n; i++) {
        answer[i] *= curPre
        answer[n - 1 - i] *= curPost
        curPre *= nums[i]
        curPost *= nums[n - 1 - i]
    }

    return answer
}
```

## Submission

    Success

    Runtime: 84 ms, faster than 83.93% of TypeScript online submissions for Product of Array Except Self.

    Memory Usage: 63.7 MB, less than 31.16% of TypeScript online submissions for Product of Array Except Self.