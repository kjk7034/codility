# Task name: Triangle

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    const len = A.length;
    const sortData = A.sort((a,b)=>a-b)
    if(len < 3) {
        return 0;
    }
    for(let i = 2;i<len;i++) {
        if(sortData[i] < sortData[i-1] + sortData[i-2]) {
            return 1
        }
    }
    return 0
}
```

## Result 

100%
