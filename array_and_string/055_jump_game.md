# 55. Jump Game
## Inputs

    nums - Array of integers

## Outputs

    Boolean - True if you can reach the last index, else false


## Constraints

    index progression <= nums[i]
    1 <= nums.length <= 104
    0 <= nums[i] <= 105


## Psudo-code

    function canJump(nums) {
        n = nums.length
        location = n - 1

        // Work from the last index back
        for i = location - 1; i >= 0; i--
            // See if it is reachable by any other index
            if nums[i] >= location - i
                // Update the position to work back from
                location = i
        
        // Return true if final location is 0
        return location === 0
    }

## Code

```js
function canJump(nums: number[]): boolean {
    const n = nums.length

    let location = n - 1
    for (let i = location - 1; i >= 0; i--) {
        if (nums[i] >= location - i) location = i
    }

    return location === 0
}
```
## Submission

    Success

    Runtime: 56 ms, faster than 96.07% of TypeScript online submissions for Jump Game.
    
    Memory Usage: 54.6 MB, less than 57.41% of TypeScript online submissions for Jump Game.