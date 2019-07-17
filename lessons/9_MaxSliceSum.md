# Task name: MaxSliceSum

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    const len = A.length;
    let max = A[0];
    let stackSum = 0;
    if(len === 0) {
        return 0;
    }
    for(let i=0;i<len;i++){
        if(max < stackSum + A[i]) {
            max = stackSum + A[i];
            continue;
        } else if ( max < A[i]) {
            max = A[i];
            continue;
        }
        stackSum = A[i];
    }
    return max;
}
```

## Result 

30%

## Solution 2

```javascript
function solution(A) {
    const len = A.length;
    let max = A[0];
    let stackSum = 0;
    if(len === 0) {
        return 0;
    }
    for(let i=0;i<len;i++){
        if(max < stackSum + A[i]) {
            max = stackSum + A[i];
            stackSum = 0;
        } else if ( max < A[i]) {
            max = A[i];
            stackSum = 0;
        } else {
            stackSum = (stackSum + A[i]) > 0 ? stackSum + A[i] : 0;
        }
    }
    return max;
}
```

## Result 

53%

## Solution 3

```javascript
function solution(A) {
     const len = A.length;
    let max = A[0];
    let stackSum = 0;
    if(len === 0) {
        return 0;
    }
    for(let i=0;i<len;i++){
        max = Math.max(max, stackSum + A[i]);
        stackSum = Math.max(0, stackSum + A[i]);
    }
    return max;
}
```

## Result 

100%