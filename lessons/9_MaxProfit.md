# Task name: MaxProfit

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    const len = A.length;
    if(len < 2) {
        return 0;
    }
    let min = A[0];
    let max = A[1];
    for(let i = 0;i < len-1;i++) {
        if(A[i] < min) {
            min = A[i];
        } else if(A[i+1] > max) {
            max = A[i+1];
        }
    }
    return max - min;
}
```

## Result 

44%

## Solution 2

```javascript
function solution(A) {
    const len = A.length;
    if(len < 2) {
        return 0;
    }
    
    let min = A[0], profit = 0, priceGap = 0;
    
    for(let i = 1;i < len;i++) {
        min = Math.min(A[i], min);
        priceGap = Math.max(0, A[i] - min);
        profit = Math.max(profit, priceGap);
    }
    return profit;
}
```

## Result 

100%