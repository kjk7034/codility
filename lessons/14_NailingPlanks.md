# Task name: NailingPlanks

120 minutes for 1 task

## Solution 1

```javascript
function solution(A, B, C) {
    const len = A.length;
    const cLen = C.length;
    let min = 0;
    let max = 0;
    for(let i=0;i<len;i++){
        min = Math.max(min, A[i]);
        max = Math.max(max, B[i]);
    }
    for(let i=0;i<cLen;i++){
        if(C[i] >= min) {
            return i + 1;
        }
    }
    return -1;
}
```

## Result 

12%

## Solution 2

```javascript
function solution(A, B, C) {
    let begin = 0, end = C.length - 1, result = -1;
    
    while (begin <= end) {
        const mid = parseInt((begin + end) / 2);
        if (check(A, B, C, mid+1)) {
            end = mid - 1;
            result = mid+1;
        } else {
            begin = mid + 1;
        }
    }
    return result;
}
function check(a, b, c, num) {
    const pNails = new Array(2*c.length + 1).fill(0);
    for (let i = 0; i < num; i++) {
        pNails[c[i]]++;
    }
    for (let i = 1; i < pNails.length; i++) {
        pNails[i] += pNails[i-1];
    }
    for (let i = 0; i < a.length; ++i) {
        if (pNails[b[i]] <= pNails[a[i]-1]) return false;
    }
    return true;
}
```

## Result 

100%