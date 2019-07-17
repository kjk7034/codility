# Task name: CountDiv

120 minutes for 1 task

## Solution 1

```javascript
function solution(A, B, K) {
    const diff = B-A;
    let count = 0;
    for(let i = 0;i <= diff ; i++) {
       if((i+A)%K === 0){
           count++;
       }
    }
    return count;
}
```

## Result 

50%

## Solution 2

```javascript
function solution(A, B, K) {
    return Math.floor(B/K) - Math.floor((A-1)/K);
}
```

## Result 

100%