# Task name: MinAbsSumOfTwo

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
   const len = A.length;
    let min = Math.abs(A[0]+A[0]);
    for(let p=0;p<len;p++){
        let q = p;
        while(q<len) {
            min = Math.min(min, Math.abs(A[p]+A[q]));
            q++
        }
    }
    return min;
}
```

## Result 

45%

## Solution 2

```javascript
function solution(A) {
   const len = A.length;
    let p = 0; q = len-1;
    A.sort((a,b)=>a-b);
    let minAbsSum = Math.abs(A[p]+A[q]);
    while(p <= q){
        const currentAbsSum = A[p]+A[q];
        minAbsSum = Math.min(minAbsSum, Math.abs(currentAbsSum));
        if(currentAbsSum <= 0){
            p++
        } else {
            q--
        }
    }
    return minAbsSum;
}
```

## Result 

100%
