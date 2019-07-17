# Task name: PassingCars

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    let result = 0;
    let eastCount = 0;
    for(let i in A) {
        if(A[i] === 0) {
            eastCount++;
        } else {
            result += eastCount;
        }
        if(result > 1000000000) {
            return -1
        }
    }
    return result;
}
```

## Result 

100%