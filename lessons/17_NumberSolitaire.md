# Task name: NumberSolitaire

120 minutes for 1 task

## Solution 1

```javascript
function solution(M, A) {
    let len = A.length;
    const scores = new Array(len);
    
    scores[0] = A[0];
    for(let i=1;i<len;i++) {
        let max = scores[i-1] + A[i];
        for(let j=1;j<=6;j++) {
            if(i >= j) {
                max = Math.max(scores[i-j] + A[i], max);
            }
        }
        scores[i] = max;
    }
    return scores[len-1];
}
```

## Result 

100%
