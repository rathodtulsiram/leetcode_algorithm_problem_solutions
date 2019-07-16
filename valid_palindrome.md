# [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/)

Given a non-empty string s, you may delete at most one character. Judge whether you can make it a palindrome.

Given a string, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases.

**Note:** For the purpose of this problem, we define empty string as valid palindrome.

Example 1:
```
Input: "A man, a plan, a canal: Panama"
Output: true
```

Example 2:
```
Input: "race a car"
Output: false
```

# Solution
```
/**
 * @return is valid palindrome
 */
fun isPalindrome(s: String): Boolean {
    val regex = Regex("[^A-Za-z0-9]") // alphanumeric regex
    val charSequence = regex.replace(s, "").toLowerCase()
    val length = charSequence.length

    for (index in 0 until length / 2) {
        if (charSequence[index] != charSequence[length - index - 1]) {
            return false
        }
    }

    return true
}
```
