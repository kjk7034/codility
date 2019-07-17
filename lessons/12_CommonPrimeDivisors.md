# Task name: CommonPrimeDivisors

120 minutes for 1 task

## Solution 1

```javascript
function solution(A) {
    let result = 0;
    const len = A.length;
    for(let i=0;i<len;i++){
        let a = A[i];
        let b = B[i];
        const gcd_ab = gcd(a,b);
        let gcd_a = 0;
        let gcd_b = 0;

        while (gcd_a !== 1) {
            gcd_a = gcd(a, gcd_ab);
            a /= gcd_a
        }
        
        while (gcd_b !== 1) {
            gcd_b = gcd(b, gcd_ab);
            b /= gcd_b
        }
        if(a === 1 && b === 1) {
            result++;
        }
    }
    return result;
}
function gcd(a, b) {
	return b ? gcd(b, a % b) : a;
}
```

## Result 

62%