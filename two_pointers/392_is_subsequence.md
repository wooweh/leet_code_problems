# 392. Is Subsequence

## Inputs

s - string
t - string

## Outputs

boolean - True if s is subsequence of t, else false

## Constraints

0 <= s.length <= 100
0 <= t.length <= 10^4
s and t consist only of lowercase English letters.

## Psudo-code

    function isSubsequence(s, t) {
        // Edge cases
        if s.length === 0 then return true
        if t.length === 0 then return false

        m = s.length - 1
        n = t.length - 1
        i = 0

        // Iterate through letters of t 
        for j = 0, j < n, j++
            // Incriment i each time it matched
            If t[j] = s[i] then incriment i
            // If letter at last index of s matches then return true
            if t[j] = s[m] then
                return true

        return false

    }

## Code

```js
function isSubsequence(s: string, t: string): boolean {
  if (s.length === 0) return true;
  if (t.length === 0) return false;

  const m = s.length - 1;
  const n = t.length;
  let i = 0;

  for (let j = 0; j < n; j++) {
    if (t[j] === s[i]) {
      if (i === m) return true;
      i += 1;
    }
  }

  return false;
}
```

## Submission

Success

Runtime: 62 ms, faster than 38.76% of TypeScript online submissions for Is Subsequence.

Memory Usage: 51.1 MB, less than 35.21% of TypeScript online submissions for Is Subsequence.
