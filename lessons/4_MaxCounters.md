# Task name: MaxCounters

120 minutes for 1 task

## Solution 1

```javascript
function solution(N, A) {
    const maxCounter = N+1;
    let counters = new Array(N);
    counters.fill(0);
    
    let max = 0;
    for(let i in A) {
        const counterIndex = A[i] - 1;
        if(A[i] < maxCounter) {
            counters[counterIndex]++
            if(counters[counterIndex] > max) {
                max = counters[counterIndex];
            }
        } else {
            for(let j=0;j<N;j++){
                counters[j] = max;
            }
        }
    }
    return counters
}
```

## Result 

77%

## Solution 2

```javascript
function solution(N, A) {
    
 const maxCounter = N+1;
    let counters = new Array(N);
    counters.fill(0);
    
    let currentMax = 0;
    let lastCalledMax = 0;
    for(let i in A) {
        if(A[i] < maxCounter) {
            const counterIndex = A[i] - 1;
            if(counters[counterIndex] < lastCalledMax) {
                counters[counterIndex] = lastCalledMax + 1;
            } else {
                counters[counterIndex]++    
            }
            if(counters[counterIndex] > currentMax) {
                currentMax = counters[counterIndex];
            }
        } else {
            lastCalledMax = currentMax;
        }
    }
    for(let j = 0; j < N; j++){
        if(counters[j] < lastCalledMax){
            counters[j] = lastCalledMax
        }
    }
    return counters
}
```

## Result 

100%
