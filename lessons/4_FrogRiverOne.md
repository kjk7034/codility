# Task name: FrogRiverOne

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    return A.findIndex((v)=> v=== X)
}
```

## Result 

18%

다음의 내용을 확인 ㅠ.ㅜ
개구리 : 1 to X 까지의 모든 위치가 잎으로 덮어져 있을 때 강 건너편으로 이동할 수 있다.
만약 개구리가 강을 건널 수 없다면 -1 리턴

## Solution 2

```javascript
function solution(A) {
   const control = new Set()
    for(i in A) {
        if(A[i] <= X) {
            control.add(A[i])
        }
        if(control.size === X) {
            return Number(i)
        }
    }
    return -1
}
```

## Result 

100%