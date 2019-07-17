# Task name: Nesting

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    const len = S.length;
    let opener = 0;
    let closer = 0;

    for(let i = 0;i<len;i++) {
        if(S.charAt(i) === "(") {
            opener++;
        }
        if(S.charAt(i) === ")") {
            closer++;
        }
    }
    return closer === opener ? 1 : 0;
}
```

## Result 

12%

## Solution 2

```javascript
function solution(A) {
    const len = S.length;
    
    const stack = [];
    for(let i = 0;i<len;i++) {
        if(S.charAt(i) === "(") {
            stack.push(S.charAt(i))
        } else if(S.charAt(i) === ")") {
            if(stack.length === 0) {
                return 0;
            }
            const lastString = stack.pop();
            if(lastString !== "(") {
                return 0;
            }
        }
    }
    if(stack.length !== 0) {
        return 0;
    }
    return 1;
}
```

## Result 

100%