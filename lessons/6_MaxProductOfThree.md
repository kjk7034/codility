# Task name: MaxProductOfThree

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    const sortData = A.sort();
    const len = A.length;
    return sortData[len-1] * sortData[len-2] * sortData[len-3]
}
```

## Result 

23%

## Solution 2

```javascript
function solution(A) {
    const sortData = A.sort();
    const len = A.length;
    if(sortData[0] * sortData[1] > sortData[len-2] * sortData[len-3]) {
        return sortData[len-1] * sortData[0] * sortData[1]
    }
    return sortData[len-1] * sortData[len-2] * sortData[len-3]
}
```

## Result 

44%
아..... sort...

## Solution 2

```javascript
function solution(A) {
    const len = A.length;
    const sortData = A.sort((a, b)=> a-b);
    return Math.max(sortData[0]*sortData[1]*sortData[len-1], sortData[len-3]*sortData[len-2]*sortData[len-1])
}
```

## Result 

100%