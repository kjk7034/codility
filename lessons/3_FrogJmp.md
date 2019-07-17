# Task name: FrogJmp

120 minutes for 1 task

## Solution

```javascript
function solution(X, Y, D) {
    if(X === Y) {
        return 0
    } else if(D >= (Y-X)) {
        return 1
    }
    let jumps = Math.floor((Y-X)/D);
    if((Y-X)%D > 0) {
        jumps += 1
    }
    return jumps
}
```

## Result 

100%