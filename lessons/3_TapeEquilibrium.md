# Task name: TapeEquilibrium

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    let min
    A.forEach((v, i)=>{
        if(i > 0) {
            const firstPart = A.slice(0,i);
            const secondPart = A.slice(i,A.length);
            const result =  Math.abs(firstPart.reduce((a,b)=>a+b)-secondPart.reduce((a,b)=>a+b))
            if(!min || min > result) {
                min = result
            }
        }
    })
    return min
}
```

## Result 

30%

## Solution 2

```javascript
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    const total = A.reduce((a,b)=> a+b);
    let firstPart = 0;
    let secondPart = 0;
    let min
    A.forEach((v, i)=>{
        firstPart += v;
        secondPart = total - firstPart;
        const diff = Math.abs(firstPart - secondPart);
        min = min ? Math.min(min, diff) : diff;
    })
    return min
}
```
## Result 

46%

## Solution 3

```javascript
function solution(A) {
    // write your code in JavaScript (Node.js 8.9.4)
    const size = A.length;
    let first = [size];
    let second = [size];
    A.forEach((v, i)=>{
        if(i === 0) {
            first[i] = 0;
        } else {
            first[i] = first[i-1] + A[i-1];
        }
        const iReverse = size - i - 1
        if(iReverse === size - 1) {
            second[iReverse] = A[iReverse]
        } else {
            second[iReverse] = second[iReverse+1] + A[iReverse]
        }
    })
    let min = Math.abs(first[1] - second[1])
    
    for(let j = 2;j<A.length;j++){
        const diff = Math.abs(first[j] - second[j])
        if(min > diff) {
            min = diff;
        }
    }
    return min
}
```
## Result 

100%