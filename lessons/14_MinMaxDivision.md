# Task name: MinMaxDivision

120 minutes for 1 task

## Solution 1

```javascript
function solution(K, M, A) {
    const len = A.length;
    let minSum = 0;
    let maxSum = 0;
    
    for(let i=0;i<len;i++){
        maxSum = maxSum + A[i];
        minSum = Math.max(minSum, A[i]);
    }
    
    while(minSum <= maxSum){
        const midSum = parseInt((minSum + maxSum) /2);
        const ok = checkDivisable(midSum, K, A);
        if(ok) {
            possibleResult = midSum;
            maxSum = midSum - 1; 
        } else {
            minSum = midSum + 1;
        }
    }
    return possibleResult;
}
function checkDivisable (midSum, K, A){
    let numBlockAllowed = K;
    let currentBlockSum = 0;
    const len = A.length;
    for(let i=0; i< len; i++){
        currentBlockSum = currentBlockSum + A[i];
        
        if(currentBlockSum > midSum){
            numBlockAllowed--;
            currentBlockSum = A[i];
        }
        
        if(numBlockAllowed == 0){
            return false; 
        }
    }
    return true;   
}
```

## Result 

100%