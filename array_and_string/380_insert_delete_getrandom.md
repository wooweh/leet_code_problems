# 380. Insert Delete GetRandom O(1)
## Inputs

    Initialisation of a class and calls to the methods defined in the class.

## Outputs

    Methods:
        insert(val) - True if val does not exist in set, else false
        remove(val) - True if val exists in set, else false
        getRandom() - Any val with equal probability

## Constraints  

    231 <= val <= 231 - 1
    At most 2 * 10^5 calls will be made to insert, remove, and getRandom.
    There will be at least one element in the data structure when getRandom is called.

## Psudo-code

    class RandomizedSet {
        randomizedSet() {
            this.values = []
            this.indexByValue = new Map
        }

        insert(val) {
            if val not in this.indexByValue
                push to this.values
                this.indexByValue.set(val, this.values.length - 1)
                return true
            else
                return false

        }

        remove(val) {
            if val not in this.indexByValue
                return false
            else
                indexToSwap = this.indexByValue.get(val)
                if indexToSwap !== this.values.length - 1
                    temp = this.values[indexToSwap]
                    this.values[indexToSwap] = this.values[this.values.length - 1]
                    this.values[this.values.length - 1] = temp
                    this.valuesByIndex.set(this.values[indexToSwap], indexToSwap)
                this.valuesByIndex.delete(val)
                this.values.pop()
      }

        getRandom() {
            index = random() * this.values.length - 1 rounded to nearest integer 
            return this.values[index]
        }
    }

## Code

```js
class RandomizedSet {
    values: number[]
    indexByValue: Map<number, number>
    
    constructor() {
        this.values = []
        this.indexByValue = new Map()
    }

    insert(val: number): boolean {
        if (!this.indexByValue.has(val)) {
            this.values.push(val)
            this.indexByValue.set(val, this.values.length - 1)
            return true
        } else {
            return false
        }
    }

    remove(val: number): boolean {
        if (!this.indexByValue.has(val)) {
            return false
        } else {
            const n = this.values.length
            const indexToSwap = this.indexByValue.get(val)
            if (indexToSwap !== n - 1) {
                const temp = this.values[indexToSwap]
                this.values[indexToSwap] = this.values[n - 1]
                this.values[n - 1] = temp

                this.indexByValue.set(
                    this.values[indexToSwap], 
                    indexToSwap
                )
            }
            this.indexByValue.delete(val)
            this.values.pop()
            return true
        }
    }

    getRandom(): number {
        const index = Math.floor(Math.random() * this.values.length)
        return this.values[index]
    }
}
```

## Submission

    Success

    Runtime: 356 ms, faster than 56.03% of TypeScript online submissions for Insert Delete GetRandom O(1).

    Memory Usage: 103.1 MB, less than 7.35% of TypeScript online submissions for Insert Delete GetRandom O(1).