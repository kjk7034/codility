# Task name: CountDistinctSlices

120 minutes for 1 task

## Solution 1

```javascript
function solution(M, A) {
    const len = A.length;
    if(len < 3) {
        return 0;
    }
    let p = 0, q = 1, r = 2, result = 0;
    A.sort((a,b)=> a-b);
    
    for(let p = 0; p < len - 2 ; p++) {
        for(let q = p+1;q<len-1;q++) {
            r = q+1;
            while (r < len && A[p] + A[q] > A[r]) {
                r++
            }
            result += r - q - 1;
        }
    }    
    return result;
}
```

## Result 

90%
