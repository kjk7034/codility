# Task name: OddOccurrencesInArray

120 minutes for 1 task

## Solution

```javascript
function solution(A) {
    let result = 0;
    for(const value of A ){
        result ^= value
    }
    return result
}
```

## Result 

100%