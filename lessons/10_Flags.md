# Task name: Flags

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    const len = A.length;
    if(len < 3) {
        return 0;
    }
    const peaks = new Array();
    let flagCount = 0;
    for(let i=1;i<len-1;i++){
        if(A[i] > A[i-1] && A[i] > A[i+1]) {
            peaks.push(i);
        }
    }
    const peakLen = peaks.length;
    if(peakLen < 3) {
        return peakLen;
    }
    for(let K=2;K<=peakLen;K++){
        let flags = 1;
        let peak = 0;
        let next_peak = 1;
        while (peak < peakLen-1) {
            if(Math.abs(peaks[peak] - peaks[next_peak]) >= K) {
                flags += 1;
                peak = next_peak;
                next_peak = peak+1;
                
            } else {
                next_peak++;
            }
            if(next_peak === peakLen || flags === K) break;
        }
        if(flagCount > flags) {
            return flagCount;
        }
        flagCount = Math.max(flags, flagCount);
    }
    return flagCount;
}
```

## Result 

100%
