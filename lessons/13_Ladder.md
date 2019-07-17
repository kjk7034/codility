# Task name: Ladder

120 minutes for 1 task

## Solution 1

```javascript
function solution(A, B) {
    const len = A.length, fib = new Array(len + 1);
    let max = 0, result = [];

    for(let i=0;i<len;i++){
        max = Math.max(A[i], max);
    }
    
    fib[0] = 1;
    fib[1] = 1;

    for(let i=2;i<=max;i++){
        fib[i] = fib[i-1] + fib[i-2];
    }
    
    for(let i=0;i<len;i++){
        result[i] = fib[A[i]] % Math.pow(2,B[i]);
    }
    return result;
}
```

## Result 

37%

## Solution 2

```javascript
function solution(A, B) {
    // write your code in JavaScript (Node.js 8.9.4)
    const len = A.length, fib = new Array(len + 1);
    let max = 0, result = [];

    for(let i=0;i<len;i++){
        max = Math.max(A[i], max);
    }
    
    fib[0] = 1;
    fib[1] = 1;

    for(let i=2;i<=max;i++){
        fib[i] = (fib[i-1] + fib[i-2])% Math.pow(2, 30);
    }
    
    for(let i=0;i<len;i++){
        result[i] = fib[A[i]] % Math.pow(2,B[i]);
    }
    return result;
}
```

## Result 

100%