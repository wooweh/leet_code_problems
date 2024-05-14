# 11. Container With Most Water

## Inputs

height - array of integers

## Outputs

integer - maximum area calculated as height (lowest of two containing indexes) multiplied by width (highest index minus lowest index)

## Constraints

n == height.length
2 <= n <= 10^5
0 <= height[i] <= 10^4

## Psudo-code

    function maxArea(height) {
        // Utility function to calculate area
        function calcArea(startHeight, endHeight, width) {
            return min(startHeight, endHeight) * width
        }

        n = height.length

        // Track highest area, left verticle and right verticle positions
        highestArea = 0
        left = 0
        right = n - 1

        // Edge case if height length is 2
        if height.length === 2 return calcArea(height[0], height[1], 1)

        // while right is less than left
        while left < right
            // Calculate area and if larger than highestArea, make highestArea
            const area = calcArea(left height, right height, left - right)
            highestArea = max(highestArea, area)

            // if left is lower than right then increment left
            if height[left] < height[right] then left += 1

            // if right is lower than left then decrement right
            if height[right] < height[left] then right -= 1
            
            // if right and left are equal then increment left and decrement right
            if height[right] === height[left]
                then right -= 1, left += 1

        return highestArea
    }

## Code

```js
function maxArea(height: number[]): number {
  function getArea(startHeight: number, endHeight: number, width: number) {
    return startHeight <= endHeight ? startHeight * width : endHeight * width;
    return Math.min(startHeight, endHeight) * width;
  }

  const n = height.length;

  let highestArea = 0;
  let left = 0;
  let right = n - 1;

  if (n === 2) return getArea(height[0], height[1], 1);

  while (left < right) {
    const leftHeight = height[left];
    const rightHeight = height[right];
    const width = right - left;
    const area = getArea(leftHeight, rightHeight, width);

    highestArea = Math.max(highestArea, area);

    if (leftHeight < rightHeight) left += 1;
    if (leftHeight > rightHeight) right -= 1;
    if (leftHeight === rightHeight) {
      left += 1;
      right -= 1;
    }
  }

  return highestArea;
}
```

## Submission

Success

Runtime: 75 ms, faster than 42.22% of TypeScript online submissions for Container With Most Water.

Memory Usage: 59.3 MB, less than 29.71% of TypeScript online submissions for Container With Most Water.
