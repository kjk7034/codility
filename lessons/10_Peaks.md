# Task name: Peaks

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    const len = A.length;
    let peakCount = 0;
    for(let i=1;i<len-1;i++){
        if(A[i] > A[i-1] && A[i] > A[i+1]){
            peakCount++;
        }
    }
    return peakCount;
}
```

## Result 

45%

## Solution 2

```javascript
function solution(A) {
    const len = A.length;
    const peaks = new Array();
    
    if(len < 3) {
        return 0;
    }
    
    for(let i=1;i<len-1;i++){
        if(A[i] > A[i-1] && A[i] > A[i+1]){
            peaks.push(i);
        }
    }
    
    const peaksSize = peaks.length;
    if(peaksSize < 3) return peaksSize;
    
    let flag, factor, result = 1, rangeStart, rangeEnd, index;
    for(let j=3;j<=peaksSize;j++){
        if(len%j !== 0) {
            continue;
        }
        factor = len/j;
        index = 0;
        for(let k=0;k<j;k++) {
            flag = false;
            rangeStart = k * factor;
            rangeEnd = (k+1) * factor;
            while(index < peaksSize && rangeStart <= peaks[index] && rangeEnd > peaks[index]) {
                flag = true;
                ++index;
            }
            if(!flag) break;
        }
        if(flag) {
            result = j;
        }
    }
        
    return result;
}
```

## Result 

100%