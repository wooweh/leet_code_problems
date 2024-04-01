# 383. Ransom Note
## Inputs

    ransomNote - String
    magazine - String

## Outputs

    Boolean, true if ransomNote can be constructed by using the letters from magazine else false.

## Constraints

    1 <= ransomNote.length, magazine.length <= 10^5
    ransomNote and magazine consist of lowercase English letters.
    Each letter in magazine can only be used once in ransomNote.

## Psudo-code

    function canConstruct(ransomNote, magazine) {
        buffer1 = ransomNote.split into array
        buffer2 = magazine.split into array
        
        if ransomNote.length > magazine.length return false
        
        let success = true
        for let i = 0; i < buffer1.length; i++
            if (success === true) 
                for let j = 0 ; j < buffer2.length; j++
                    if buffer1[i] === buffer2[j]
                        buffer2[j] = undefined // to remove used character
                        success = true
                        break
                    else
                        success = false

            else 
                return success
            
        return success
    }

## Code

```js
function canConstruct(ransomNote: string, magazine: string): boolean {
    const buffer1 = ransomNote.split('')
    const buffer2 = magazine.split('')

    if (ransomNote.length > magazine.length) return false

    let success = true
    for (let i = 0; i < buffer1.length; i++) {
        if (!!success) {
            for (let j = 0; j < buffer2.length; j++) {
                if (buffer1[i] === buffer2[j]) {
                    buffer2[j] = undefined
                    success = true
                    break
                } else {
                    success = false
                }
            }
        } else {
            return success
        }
    }
    return success

}
```

## Submission

    Success

    Runtime: 66 ms, faster than 89.50% of TypeScript online submissions for Ransom Note.

    Memory Usage: 53.6 MB, less than 58.08% of TypeScript online submissions for Ransom Note.
