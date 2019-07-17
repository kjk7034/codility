# Task name: CountSemiprimes

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
   const flags = new Array(N+1);
    let semiPrimeCount = 0;
    const semiPrimeArray = new Array(N+1)
    const pLen = P.length;
    const result = new Array(pLen);
    
    flags.fill(0); // flags 0 : prime, 1: no prime, 2: semiprime
    semiPrimeArray.fill(0);
    flags[0] = 1;
    flags[1] = 1;
    
    for(let i=2;i*i<=N;i++){
        if(flags[i]===1){
            continue;
        }
        let k = i*i;
        while(k<=N){
            if(flags[i] === 0 && flags[k/i] === 0 ) {
                flags[k] = 2;    
            } else {
                flags[k] = 1;    
            }
            k += i;
        }
    }
    
    for(let i=2;i<=N;i++){
        if(flags[i] === 2) {
            semiPrimeCount++;
        }
        semiPrimeArray[i] = semiPrimeCount;
    }
    
    for(let i=0;i<pLen;i++){
        result[i] = semiPrimeArray[Q[i]] - semiPrimeArray[P[i]-1];
    }
    return result;
}
```

## Result 

100%
