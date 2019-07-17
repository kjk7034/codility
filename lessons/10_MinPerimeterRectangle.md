# Task name: MinPerimeterRectangle

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    let factor = 1;
    let side = 1;
    
    while (factor * factor <= N) {
        if(N%factor===0){
            side = factor;
        }
        factor++
    }
    return 2*(side + N/side);
}
```

## Result 

100%
