# 27. Remove Element
## Inputs

    nums - Array of integers
    val - Integer

## Outputs

    Number of elements in nums which are not equal to val.

## Constraints

    0 <= nums.length <= 100
    0 <= nums[i] <= 50
    0 <= val <= 100

## Psudo-code

    function removeElement(nums, val) {
        k = 0
        for i = 0; i < length of nums; i++
            if nums[i] === val
                for j = length of nums - 1; j > i; j--
                    if nums[j] === val
                        continue
                    else
                        swap elements
                        k += 1
                        break
            else
                k += 1
                continue
        
        return k
    }

## Code

```js
function removeElement(nums: number[], val: number): number {
    let k = 0
    for (let i = 0; i < nums.length; i++) {
        if (nums[i] === val) {
            for (let j = nums.length - 1; j > i; j--) {
                if (nums[j] === val) continue
                [nums[i], nums[j]] = [nums[j], nums[i]]
                k += 1
                break
            }
        } else {
            k += 1
            continue
        }
    }
    return k
}
```

## Submission

    Success

    Runtime: 56 ms, faster than 67.81% of TypeScript online submissions for Remove Element.

    Memory Usage: 51.1 MB, less than 91.90% of TypeScript online submissions for Remove Element.