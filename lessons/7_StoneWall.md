# Task name: StoneWall

120 minutes for 1 task

## Solution 1

```javascript
function solution(H) {
    const len = H.length;
    const stack = [];
    let block = 0;
    let i = 0;
    while (i<len) {
        if(stack.length === 0 || H[i] > stack[stack.length-1]) {
            stack.push(H[i]);
            block++;
        } else if (H[i] < stack[stack.length-1]) {
            stack.pop();
            if(stack.length > 0) {
                continue;
            }
            stack.push(H[i]);
            block++;
        }
        i++;       
    }
    return block;
}
```

## Result 

100%
