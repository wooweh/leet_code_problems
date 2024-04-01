# 36. Valid Sudoku
## Inputs
    Array of Arrays of strings 0 to 9 - Matrix containing rows of Sudoku puzzle

## Outputs
    Boolean - True is rules are met, esle false.

    Rules:
    1. Each row must contain the digits 1-9 without repetition.
    2. Each column must contain the digits 1-9 without repetition.
    3. Each of the nine 3 x 3 sub-boxes of the grid must contain the digits 1-9 without repetition.

## Constraints

    board.length == 9
    board[i].length == 9
    board[i][j] is a digit 1-9 or '.'

## Psudo-code

    function isValidSudoku(board) {
        initialise a set
        function isUnique(item) {
            if item in set return false
            else
                add item
                return true
        }

        for row = 0; row < 9; row++
            for col = 0; col < 9; col++
                const char = board[row][col]
                if (char === ".") continue
                if (
                    !isUnique(char + "@row" + row) or
                    !isUnique(char + "@col" + col) or
                    !isUnique(char + "@box" + Math.floor(row/3) + Math.floor(col/3))
                ) {
                    return false
                }

        return true
    }

## Code

```js
function isValidSudoku(board: string[][]): boolean {
    const s = new Set()
    function isUnique(item) {
        if (s.has(item)) return false
        s.add(item)
        return true
    }

    for (let row = 0; row < 9; row++) {
        for (let col = 0; col < 9; col++) {
            const char = board[row][col]
            if (char === ".") continue
            if (
                !isUnique(char + "@row" + row) ||
                !isUnique(char + "@col" + col) ||
                !isUnique(
                    char + "@box" + Math.floor(row/3) + Math.floor(col/3)
                )
            ) {
                return false
            }
        }
    }

    return true
}
```

## Submission

    Success

    Runtime: 62 ms, faster than 90.59% of TypeScript online submissions for Valid Sudoku.

    Memory Usage: 53.2 MB, less than 72.09% of TypeScript online submissions for Valid Sudoku.