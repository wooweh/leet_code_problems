# 274. H-Index
## Inputs

    citations - Array of integers

## Outputs

    H-Index - Integer

    H-Index is the maximum value where at least h index's contain a value greater or equal to h

## Constraints

    n == citations.length
    1 <= n <= 5000
    0 <= citations[i] <= 1000

## Psudo-code

    function hIndex(citations) {
        // Sort citations in descending order
        buffer1 = citations.sort(descending)

        // Boundary conditions for n = 0 and 1
        if n === 0 return 0
        if n === 1 return 1 if citations[0] > 0 else return 0

        // Walk forward through the sorted array
        for i = 0; i < buffer1 length; i++
            // Stop at the index where the value is less than the index
            if buffer1[i] < i + 1
            // Return index as h index
            return i

        // Return n if loop continues to end
        return n
    }

## Code

```js
function hIndex(citations: number[]): number {
        const n = citations.length
        const buffer1 = citations.sort((a, b) => b - a)
        if (n === 0) return 0
        if (n === 1) return citations[0] > 0 ? 1 : 0

        for (let i = 0; i < n; i++) {
            if (buffer1[i] < i + 1) {
                return i
            }
        }

        return n
}
```

## Submission

    Success

    Runtime: 48 ms, faster than 96.30% of TypeScript online submissions for H-Index.

    Memory Usage: 51.8 MB, less than 32.29% of TypeScript online submissions for H-Index.