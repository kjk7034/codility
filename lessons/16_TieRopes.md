# Task name: TieRopes

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    const len = A.length;
    let rope = 0
    let sum = 0;
    for(let i=0;i<len;i++){
        if(sum + A[i] >= K) {
            rope++;
            sum = 0;
        } else {
            sum += A[i];
        }
    }
    return rope;
}
```

## Result 

100%
