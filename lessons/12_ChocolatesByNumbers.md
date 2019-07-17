# Task name: ChocolatesByNumbers

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    let eat = 0;
    const chocolates = new Array(N);
    chocolates.fill(1);
    for(let i=0;i<N;i++){
        if(chocolates[M*i%N] === 1) {
            chocolates[M*i%N] = 0;
            eat++;
        } else if(chocolates[M*i%N] === 0) {
            return eat;
        }
    }
    return eat;
}
```

## Result 

62%

## Solution 2

```javascript
function solution(A) {
    const gcdFunc = (a,b)=> b ? gcdFunc(b, a % b) : a;
    return N/gcdFunc(N, M)
}
```

## Result 

100%