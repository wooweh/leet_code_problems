# 167. Two Sum II - Input Array Is Sorted

## Inputs

numbers - 1-indexed array of integers sorted in ascending order
target - integer

## Outputs

array of 2 indices (index + 1) that add up to target

## Constraints

2 <= numbers.length <= 3 * 10^4
-1000 <= numbers[i] <= 1000
numbers is sorted in non-decreasing order.
-1000 <= target <= 1000
The tests are generated such that there is exactly one solution.

## Psudo-code

    function twoSum(numbers, target) {
        n = numbers.length

        // Iterate through numbers indexes
        for i = 0; i < n; i ++
            // Iterate through remaining numbers indexes
            for j = i + 1; j < n; j ++
            // If outer loop plus inner loop > target then break
            // If outer loop plus inner loop index value equals target
                if numbers[i] + numbers[j] = target
                //then return [outer + 1, inner + 1]
                    return [i + 1, j + 1]

    }

## Code

```js
function twoSum(numbers: number[], target: number): number[] {
  const n = numbers.length;
  if (n === 2) return [1, 2];

  for (let i = 0; i < n; i++) {
    for (let j = i + 1; j < n; j++) {
      if (numbers[i] + numbers[j] > target) break;
      if (numbers[i] + numbers[j] === target) return [i + 1, j + 1];
    }
  }
}
```

## Submission

Success

Runtime: 677 ms, faster than 12.21% of TypeScript online submissions for Two Sum II - Input Array Is Sorted.

Memory Usage: 51.5 MB, less than 43.30% of TypeScript online submissions for Two Sum II - Input Array Is Sorted.
