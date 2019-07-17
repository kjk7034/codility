# Task name: MaxNonoverlappingSegments

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    const len = A.length;
    let count = 1;
    let prevEnd = B[0];
    if(len <= 1) {
        return len;
    }
    for(let i=0;i<len;i++){
        if(A[i] > prevEnd) {
            count++;
            prevEnd = A[i];
        }
    }
    return count;
}
```

## Result 

50%

## Solution 2

```javascript
function solution(A) {
    const len = A.length;
    let count = 1;
    let prevEnd = B[0];
    if(len <= 1) {
        return len;
    }
    for(let i=0;i<len;i++){
        if(A[i] > prevEnd) {
            count++;
            prevEnd = B[i];
        }
    }
    return count;
}
```

## Result 

100%
