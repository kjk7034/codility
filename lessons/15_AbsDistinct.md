# Task name: AbsDistinct

120 minutes for 1 task

## Solution 1

```javascript
function solution(M, A) {
    const len = A.length;
    const setData = new Set();
    for(let i=0;i<len;i++){
        setData.add(Math.abs(A[i]));
    }
    return setData.size;
}
```

## Result 

90%
