# Task name: CountFactors

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    let result = 0;
 
    for(let i=1;i<=N;i++){
        if(N%i === 0) {
            result++
        }
    }
    return result;
}
```

## Result 

78%

## Solution 2

```javascript
function solution(A) {
    let factor = 1;
    let result = 0;
    
    while (factor * factor < N) {
        if(N%factor === 0) {
            result += 2;
        }
        factor++;
    }
    if(factor * factor === N) {
        result++;
    }
    return result;
}
```

## Result 

78%
