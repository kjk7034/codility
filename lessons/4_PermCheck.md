# Task name: PermCheck

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    const size = A.length;
    const control = [size];
    let left = 0;
    for(let i in A) {
        if(i===0) {
            left = A[i]
        }
        left = left < A[i] ? A[i] : left;
        if(!control[A[i] - 1]) {
            control[A[i] - 1] = true;
            left--;
        }
    }
    if(left !=== size) {
        return 0
    }
    return left === 0 ? 1 : 0;
}
```

## Result 

75%

## Solution 2

```javascript
function solution(A) {
    const size = A.length;
    const control = new Array(size);
    let left = 0;
    for(let i in A) {
        if(i===0) {
            left = A[i]
        }
        left = left < A[i] ? A[i] : left;
    }
    if(left !== size) {
        return 0
    }
    for(let i in A) {
        if(!control[A[i] - 1]) {
            control[A[i] - 1] = true;
            left--;
        }
    }
    return left === 0 ? 1 : 0;
}
```

## Result 

100%