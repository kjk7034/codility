# Task name: MaxDoubleSliceSum

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    let len = A.length;
    let leftMaxSum = new Array(len);
    let rightMaxSum = new Array(len);
    let max = 0;
    leftMaxSum.fill(0);
    rightMaxSum.fill(0);
    for(let i=1;i<len-1;i++){
        leftMaxSum[i] = Math.max(0, leftMaxSum[i-1] + A[i]);
    }
    for(let i=len-2;i>0;i--){
        rightMaxSum[i] = Math.max(0, rightMaxSum[i+1] + A[i]);
    }
    
    for(let i=1;i<len-1;i++){
        max = Math.max(max,leftMaxSum[i-1]+rightMaxSum[i+1]);
    }
    return max;
}
```

## Result 

100%
