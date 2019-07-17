# Task name: GenomicRangeQuery

120 minutes for 1 task

## Solution 1

```javascript
function solution(S, P, Q) {
    const sToNum = Array.from(S).map(v=>{
        let num = 4; // default T
        switch(v) {
            case "A" :
                num = 1
                break;
            case "C" :
                num = 2
                break;
            case "G" :
                num = 3
                break;
            default: 
                break;
        }
        return num;
    })
    let result = [];
    for(let i in P) {
       result[i] = Math.min(...sToNum.filter((v,i2)=> i2>=P[i] && i2<=Q[i]));
    }
    return result
```

## Result 

62%

## Solution 2

```javascript
function solution(S, P, Q) {
    const len = S.length;
    const converA = new Array(len + 1)
    const converC = new Array(len + 1)
    const converG = new Array(len + 1)
    const spliceString = S.split("")
    let result = [];
    
    converA.fill(0)
    converC.fill(0)
    converG.fill(0)
    
    for(let i = 0;i< len;i++) {
        const value = spliceString[i]
        switch(value) {
            case "A" :
                converA[i+1]++;
                break;
            case "C" :
                converC[i+1]++;
                break;
            case "G" :
                converG[i+1]++;
                break;
        }
        converA[i+1] += converA[i]
        converC[i+1] += converC[i]
        converG[i+1] += converG[i]
    }
    for(let j = 0;j<P.length;j++) {
        const q = Q[j]
        const p = P[j]
        if(q === p) {
            switch(spliceString[q]) {
                case "A" :
                    result[j] = 1
                    break;
                case "C" :
                    result[j] = 2
                    break;
                case "G" :
                    result[j] = 3
                    break;
                default :
                    // T
                    result[j] = 4
                break;
            }
        } else if(converA[q + 1] > converA[p + 1]) {
            result[j] = 1
        } else if ( converC[q + 1] > converC[p + 1]) {
            result[j] = 2
        } else if ( converG[q + 1] > converG[p + 1]) {
            result[j] = 3
        } else {
            result[j] = 4
        }
    }
    return result
```

## Result 

75%

## Solution 3

```javascript
function solution(A) {
    const len = S.length;
    const converA = new Array(len + 1)
    const converC = new Array(len + 1)
    const converG = new Array(len + 1)
    const spliceString = S.split("")
    let result = [];
    
    converA.fill(0)
    converC.fill(0)
    converG.fill(0)
    
    for(let i = 0;i< len;i++) {
        const value = spliceString[i]
        switch(value) {
            case "A" :
                converA[i+1]++;
                break;
            case "C" :
                converC[i+1]++;
                break;
            case "G" :
                converG[i+1]++;
                break;
        }
        converA[i+1] += converA[i]
        converC[i+1] += converC[i]
        converG[i+1] += converG[i]
        
    }
    for(let j = 0;j<P.length;j++) {
        const startIndex = P[j]
        const endIndex = Q[j]
        if(startIndex === endIndex) {
            switch(spliceString[startIndex]) {
                case "A" :
                    result[j] = 1
                    break;
                case "C" :
                    result[j] = 2
                    break;
                case "G" :
                    result[j] = 3
                    break;
                default :
                    // T
                    result[j] = 4
                break;
            }
        } else if(converA[startIndex] !== converA[endIndex + 1]) {
            result[j] = 1
        } else if ( converC[startIndex] !== converC[endIndex + 1]) {
            result[j] = 2
        } else if ( converG[startIndex] !== converG[endIndex + 1]) {
            result[j] = 3
        } else {
            result[j] = 4
        }
    }
    return result
}
```

## Result 

100%