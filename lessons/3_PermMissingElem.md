# Task name: PermMissingElem

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    if(!A || A.length === 0) {
       return 1
   }
   const n = A.length + 1
   return n + (n*(n-1)/2) - A.reduce((a, b)=> a+b)
}
```

## Result 

100%