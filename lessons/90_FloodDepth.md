# Task name: FloodDepth

120 minutes for 1 task

## Solution 1

```javascript
function solution(S) {
    const len = A.length;
    let highIdx = 0;
    let lowIdx = 0;
    let max = 0;
    
    for(let i=1;i<len;i++) {
        const current = A[i];
        const high = A[highIdx];
        const low = A[lowIdx];
        
        if(current > high) {
            max = Math.max(max, high - low);
            highIdx = i;
            lowIdx = i;
        } else if (current > low) {
            max = Math.max(max, current - low);
        } else if (current < low) {
            lowIdx = i;
        }
    }
    return max;
}
```

## Result 

100%