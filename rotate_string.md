# [Rotate String](https://leetcode.com/problems/sum-of-two-integers/)

We are given two strings, A and B.

A shift on A consists of taking string A and moving the leftmost character to the rightmost position. For example, if A = 'abcde', then it will be 'bcdea' after one shift on A. Return True if and only if A can become B after some number of shifts on A.

```
Example 1:
Input: A = 'abcde', B = 'cdeab'
Output: true

Example 2:
Input: A = 'abcde', B = 'abced'
Output: false
```

# Solution
```
/**
* @return is rotated string
*/
fun rotateString(A: String, B: String): Boolean {
    val charArrayA = A.toCharArray()
    val charArrayB = B.toCharArray()

    val lengthOfA = charArrayA.size
    val lengthOfB = charArrayB.size

    when {
        lengthOfA == 0 && lengthOfB == 0 -> return true
        else -> {

            val charArray = A.toCharArray()
            var tempChar: Char

            for (i in 0 until lengthOfA - 1) {
                tempChar = charArray[0]
                for (j in 0 until lengthOfA - 1) {
                    charArray[j] = charArray[j + 1]
                }
                charArray[lengthOfA - 1] = tempChar

                if (B == String(charArray)) {
                    return true
                }
            }
            return false
        }
    }
}
```

