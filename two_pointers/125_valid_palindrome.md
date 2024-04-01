# 125. Valid Palindrome
## Inputs

    s - String

## Outputs

    Boolean, true if s, after removing all non-alphanumeric characters, is a palindrome, else false.

    Palindrome - An alphanumeric string that reads the same forwards as backwards


## Constraints

    1 <= s.length <= 2 * 10^5
    s consists only of printable ASCII characters.


## Psudo-code

    function isPalindrome(s) {

        remove all non-alphanumeric characters in s
        make s lower case
        forward = s

        backward = forward.split('').reverse().join('')

        return  forward === backward
    }

## Code

```js
function isPalindrome(s: string): boolean {
    const forward = s.replace(/[^a-zA-Z0-9]/g, '').toLowerCase()
    const backward = forward.split('').reverse().join('')

    return forward === backward
}
```

## Submission

    Success

    Runtime: 65 ms, faster than 69.00% of TypeScript online submissions for Valid Palindrome.

    Memory Usage: 54.1 MB, less than 46.72% of TypeScript online submissions for Valid Palindrome.