# 45. Jump Game 2
## Inputs

    nums - Array of integers

## Outputs

    Integer - Minimum number of jumps to reach last index.

## Constraints

    1 <= nums.length <= 104
    0 <= nums[i] <= 1000
    It's guaranteed that you can reach nums[n - 1]

## Psudo-code

    function jump(nums) {
        n = nums length
        position = n - 1
        jumps = 0

        while position > 0
            for i = 0; i < position; i++
                if nums[i] + i >= position
                    position = i
                    jumps + 1
                    break
        return jumps
    }

## Code

```js
function jump(nums: number[]): number {
    const n = nums.length

    let position = n - 1
    let jumps = 0

    while (position > 0) {
        for (let i = 0; i < position; i++) {
            if (nums[i] + i >= position) {
                position = i
                jumps += 1
                break
            }
        }
    }
    return jumps
}
```
## Submission

    Success

    Runtime: 64 ms, faster than 61.24% of TypeScript online submissions for Jump Game II.

    Memory Usage: 51.7 MB, less than 90.71% of TypeScript online submissions for Jump Game II.