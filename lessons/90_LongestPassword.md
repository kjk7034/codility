# Task name: LongestPassword

120 minutes for 1 task

## Solution 1

```javascript
function solution(S) {
    const words = S.split(" ");
    let maxLength = -1;
    for(let i=0;i<words.length;i++) {
        const word = words[i];
        if(word.match("^[0-9a-zA-Z]*$") && word.replace(/[0-9]+/gim, "").length%2 === 0 && word.replace(/[a-zA-Z]+/gim, "").length%2 === 1){
            maxLength = Math.max(maxLength, word.length)
        }
    }
    return maxLength;
}
```

## Result 

100%