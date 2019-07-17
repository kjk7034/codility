# Task name: CyclicRotation

120 minutes for 1 task

## Solution 1 

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

## Solution 2

```javascript
function solution(A, K) {
   let arr = new Array(A.length);
    for(let i=0;i<A.length;i++){
        arr[(i+K)%A.length] = A[i]
    }
    return arr;
}
```

## Result 

100%

