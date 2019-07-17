# Task name: Fish

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    const stack = [];
    let fishes = 0;
    for(let i = 0;i<A.length;i++) {
        if(B[i] === 1) {
            stack.push(A[i]);
        } else {
            while(stack.length > 0){
                const lastFish = stack.pop();
                if(lastFish > A[i]) {
                    stack.push(lastFish);
                    break;
                }
            }
            if(stack.length === 0) {
                fishes++;        
            }
        }
        
    }
    return stack.length + fishes;
}
```

## Result 

100%
