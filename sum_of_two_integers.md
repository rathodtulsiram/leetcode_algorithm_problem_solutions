# [Sum of Two Integers](https://leetcode.com/problems/sum-of-two-integers/)

Calculate the sum of two integers a and b, but you are not allowed to use the operator + and -.

Example 1:
```
Input: a = 1, b = 2
Output: 3
```
Example 2:
```
Input: a = -2, b = 3
Output: 1
```
# Solution
## 1. Using bitwise shift
```
/**
* @return sum of two integer
*/
fun getSum(a: Int, b: Int): Int {
    if (b == 0) return a

    var aVal = a
    var bVal = b
    while (bVal != 0) {
        val carry = aVal and bVal
        aVal = aVal xor bVal
        bVal = carry shl 1
    }
    return aVal
}
```

## 2. Using traditional approach

```
/**
* @return sum of two integer
*/
fun getSum(a: Int, b: Int): Int {
    var aVal = a
    var bVal = b
    if (bVal > 0) {
        while (bVal > 0) {
            aVal++
            bVal--
        }
    } else {
        while (bVal < 0) {
            aVal--
            bVal++
        }
    }
    return aVal
}
```
