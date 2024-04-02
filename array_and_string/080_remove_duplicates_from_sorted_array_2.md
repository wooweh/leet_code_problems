# 80. Remove Duplicates from Sorted Array II
## Inputs

    nums - Array of integers in ascending order

## Outputs

    k - Number of elements with at most 1 duplicate per unique element.

## Constraints

    1 <= nums.length <= 3 * 10^4
    -10^4 <= nums[i] <= 10^4
    nums is sorted in ascending order.

## Psudo-code

    function removeDuplicates(nums) {
        j = 2

        for i = 2; i < nums length; i++
            if (nums[i] !== nums[j - 2])
                nums[j] = nums[i]
                j++
        
        return j
    }

## Code

```js
function removeDuplicates(nums: number[]): number {
    let j = 2
    for (i = 2; i < nums.length; i++) {
        if (nums[i] !== nums[j - 2]) {
            nums[j] = nums[i]
            j++
        }
    }

    return j
}
```
[0, 1, 1, 1, 1, 1, 2, 3, 3]

## Submission

    Success
    
    Runtime: 59 ms, faster than 84.54% of TypeScript online submissions for Remove Duplicates from Sorted Array II.
    
    Memory Usage: 52.1 MB, less than 91.72% of TypeScript online submissions for Remove Duplicates from Sorted Array II.