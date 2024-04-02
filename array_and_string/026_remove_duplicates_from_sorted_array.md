# 26. Remove Duplicates from Sorted Array
## Inputs

    nums - Array of integers sorted in ascending order.

## Outputs

    k - Number of unique elements in nums.

## Constraints

    1 <= nums.length <= 3 * 10^4
    -100 <= nums[i] <= 100
    nums is sorted in ascending order.

## Psudo-code

    function removeDuplicates(nums) {
        j = 1 // position to increment

        for i = 1; i < nums length; i++
            if (nums[i] != nums[i - 1])
                nums[j] = nums[i]
                j++

        return j        
    }

## Code

```js
function removeDuplicates(nums: number[]): number {
    let j = 1

    for (let i = 1; i < nums.length; i++) {
        if (nums[i] !== nums[i - 1]) {
            nums[j] = nums[i]
            j++
        }
    }

    return j
}
```

## Submission

    Success
    
    Runtime: 54 ms, faster than 97.47% of TypeScript online submissions for Remove Duplicates from Sorted Array.
    
    Memory Usage: 53.1 MB, less than 50.46% of TypeScript online submissions for Remove Duplicates from Sorted Array.