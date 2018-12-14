---
id: sum-all-odd-fibonacci-numbers
title: Sum All Odd Fibonacci Numbers
---

```js
function isPrime (num) {
  let isPrime = true

  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (num % i === 0) {
      isPrime = false
      break
    }
  }

  return isPrime
}

function primes (maxNum) {
  let primesArr = []

  for (let i = 2; i <= maxNum; i++) {
    if (isPrime(i)) {
      primesArr.push(i)
    }
  }

  return primesArr
}

function sumPrimes(num) {
  return primes(num).reduce((a, b) => (a + b), 0)
}
```
