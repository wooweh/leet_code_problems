# 20. Valid Parentheses
## Inputs

    s - String, containing characters limited to:
        '(', ')', '{', '}', '[' and ']'

## Outputs

    Boolean, true if string is valid, else false.

    String is valid if:
    1. Open brackets must be closed by the same type of brackets.
    2. Open brackets must be closed in the correct order.
    3. Every close bracket has a corresponding open bracket of the same type.

## Constraints

    1 <= s.length <= 10^4
    s consists of parentheses only '()[]{}'.

## Psudo-code

    function isValid(s) {
        stack = []

        for let i=0; i < s.length; i++
            if s[i] === ')' && stack[stack.length - 1] === '('
                pop from stack  
            else if s[i] === ']' && stack[stack.length - 1] === '['
                pop from stack  
            else if s[i] === '}' && stack[stack.length - 1] === '{'
                pop from stack  
            else 
                push s[i] to stack
        
        return stack.length === 0
    }

## Code

```js
function isValid(s: string): boolean {
    const stack = []

    for (let i = 0; i < s.length; i++) {
        if (s[i] === ')' && stack.at(-1) === '(') {
            stack.pop()
        } else if (s[i] === ']' && stack.at(-1) === '[') {
            stack.pop()
        } else if (s[i] === '}' && stack.at(-1) === '{') {
            stack.pop()
        } else {
            stack.push(s[i])
        }
    } 

    return stack.length === 0
}
```

## Submission

    Success

    Runtime: 66 ms, faster than 38.01% of TypeScript online submissions for Valid Parentheses.

    Memory Usage: 52.8 MB, less than 30.05% of TypeScript online submissions for Valid Parentheses.