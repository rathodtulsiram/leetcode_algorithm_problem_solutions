# [Reverse String](https://leetcode.com/problems/reverse-string/)

Write a function that reverses a string. The input string is given as an array of characters char[].

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.

You may assume all the characters consist of printable ascii characters.

# Solution
```
/**
* reverse string with n/2 complexity
*/
fun reverseString(s: CharArray): Unit {
    var temp: Char? = null
    val length = s.size
    for (i in 0 until length / 2) {
        temp = s[i]
        s[i] = s[length - i - 1]
        s[length - i - 1] = temp
    }
}
```
