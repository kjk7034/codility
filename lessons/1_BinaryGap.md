# Task name: BinaryGap

120 minutes for 1 task

## Solution

```javascript
function solution(N) {
    let result = 0, max = 0, flag = 0;
    let remainder;
    while(N > 1){
        remainder = N % 2; // 0, 1
        if(remainder) {
            flag++
            max = 0
        } else if (flag > 0 && remainder === 0) {
            max++
            if(result < max) {
                result = max;
            }
        }
        N = Math.floor(N/2);
    }
    return flag > 0 ? result : 0;
}
```

## Result 

100%