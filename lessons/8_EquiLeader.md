# Task name: EquiLeader

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    const len = A.length;
    let leader = A[0];
    let leaderCount = 1;
    let equiLeaders = 0;
    
    // get Leader
    for(let i = 0;i<len;i++){
        if(A[i] === leader) {
            leaderCount++
        } else {
            leaderCount--
        }
        if(leaderCount === 0) {
            leaderCount = 1;
            leader = A[i];
        }
    }
    
    // leader check
    let total = 0;
    for(let i = 0;i<len;i++){
        if(A[i] === leader) {
            total++
        }
    }
    if(total <= (len/2)) return 0 // leader 가 아님
    
    // equiLeaders get count
    let leftLeaderCount = 0;
    for(let i = 0;i<len;i++){
        if(A[i] === leader) {
            leftLeaderCount++
        }
        const rightLeaderCount = total-leftLeaderCount;
        if(leftLeaderCount > (i+1)/2 && rightLeaderCount > (len-i-1) /2) {
            equiLeaders++;
        }
    }
    return equiLeaders;
}
```

## Result 

100%
