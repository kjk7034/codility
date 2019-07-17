# Task name: Brackets

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    const len = S.length;
    if(len%2 === 1) {
        return 0;
    }
    const stack = [];
    for(let i = 0;i<len;i++){
        const char = S.charAt(i);
        if(char === "{" || char === "[" || char === "(") {
            stack.push(char);
        } else {
            if(stack.length === 0) {
                return 0;
            }
            const lastChar = stack.pop();
            if(!checkCloser(lastChar, char)) {
                return 0;
            }
        }
    }
    if(stack.length === 0) {
        return 1;
    }
    return 0;
}
function checkCloser(lastChar, char){
    if(lastChar === "(" && char === ")") return true;
    if(lastChar === "[" && char === "]") return true;
    if(lastChar === "{" && char === "}") return true;
    return false;
}
```

## Result 

100%
