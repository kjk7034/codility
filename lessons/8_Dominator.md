# Task name: Dominator

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    const len = A.length;
    const stack = [];
    let leaderCount = 0;
    let lastLeader = -1;
    if(len === 0) {
        return -1;
    }
    for(let i = 0;i<len;i++){
        if(stack.length === 0) {
            stack.push(A[i]);
            continue;
        }
        if(stack[stack.length -1] === A[i]) {
            stack.push(A[i]);   
        } else {
            stack.pop();
        }
    }
    if(stack.length === 0) {
        return -1;
    }
    for(let j = 0;j<len;j++){
        if(A[j]=== stack[0]) {
            leaderCount++;
            lastLeader = j;
        }
    }
    return leaderCount > len/2 ? lastLeader : -1;
}
```

## Result 

100%
