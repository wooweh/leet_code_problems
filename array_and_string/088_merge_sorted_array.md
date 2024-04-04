# 88. Merge Sorted Array
## Inputs

    nums1 - Array of numbers [Ascending order]
    nums2 - Array of numbers [Ascending order]
    m - integer [number of elements in nums1]
    n - integer [number of elements in nums2]

## Outputs

    Merged nums1 and nums2 sorted in ascending order

    Array must not be returned. Array must be assigned to nums1.

## Constraints

    nums1.length == m + n
    nums2.length == n
    0 <= m, n <= 200
    1 <= m + n <= 200
    -10^9 <= nums1[i], nums2[j] <= 10^9

## Psudo-code

    function merge(nums1, m, nums2, n) {
        buffer1 = nums1.slice(0, m)
        buffer2 = nums2

        i = 0
        while (!!buffer1.length && !!buffer2.length) 
            if buffer1[0] <= buffer2[0]
                nums1[i++] = buffer1.shift()
            else
                nums1[i++] = buffer2.shift()
        
        while (!!buffer1.length) nums1[i++] = buffer1.shift()

        while (!!buffer2.length) nums1[i++] = buffer2.shift()
    }

## Code

```js
function merge(
    nums1: number[], m: number, nums2: number[], n: number
    ): number[] {
    const buffer1 = nums1.slice(0, m)
    const buffer2 = nums2

    let i = 0
    while (!!buffer1.length && !!buffer2.length) {
        if (buffer1[0] <= buffer2[0]) {
            nums1[i++] = buffer1.shift()
        } else {
            nums1[i++] = buffer2.shift()
        }
    }

    while (!!buffer1.length) { nums1[i++] = buffer1.shift()}

    while (!!buffer2.length) { nums1[i++] = buffer2.shift()}
}
```

## Submission

    Success

    Runtime: 52 ms, faster than 85.73% of TypeScript online submissions for Merge Sorted Array.
    
    Memory Usage: 51.1 MB, less than 89.72% of TypeScript online submissions for Merge Sorted Array.