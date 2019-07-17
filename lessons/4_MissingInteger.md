# Task name: MissingInteger

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    let minInt = 1;
    const setData = new Set(A.filter(v=> v >= 1));
    const data = [...setData].sort();
    for(let i in data) {
        if(data[i] >= minInt + 1) {
            break;
        } else {
            minInt++;    
        }
    }
    return minInt;
}
```

## Result 

33%

Sort를 사용하지 않기 위하여 ... Map으로 변환.


## Solution 2

```javascript
function solution(A) {
    const myMap = new Map();
    const len = A.length;
    for(let i = 0; i < len ; i++ ) {
        myMap.set(i, false)   
    }
    for(let j = 0; j < len ; j++ ) {
        myMap.set(A[j] - 1, true)
    }
    for(let [key, value] of myMap) {
        if(!value) return key + 1;
    }
    return myMap.size + 1;
}
```

## Result 

100%