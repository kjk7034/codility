# Task name: CyclicRotation

120 minutes for 1 task

## Solution

```javascript
function solution(A, K) {
   let arr = []
    const size = A.length;
    A.forEach((v, i)=>{
      arr[(i + K) % size] = v
    })
    return arr
}
```

## Result 

25%