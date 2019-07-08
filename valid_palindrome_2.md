# [Valid Palindrome II](https://leetcode.com/problems/valid-palindrome-ii/)

Given a non-empty string s, you may delete at most one character. Judge whether you can make it a palindrome.

Example 1:
```
  Input: "aba"
  Output: True
 ``` 
Example 2:
```
  Input: "abca"
  Output: True
```
Explanation: You could delete the character 'c'.

**Note: The string will only contain lowercase characters a-z. The maximum length of the string is 50000.**

# Solution
```
/**
 * @return palindrome or not within [charSequence] and [skipCharCount]
 */
fun isPalindrome(charSequence: CharSequence, skipCharCount: Int = 0): Boolean {
    if (charSequence.isEmpty()) {
        return false
    }

    val length = charSequence.length
    for (i in 0 until length / 2) {
        if (charSequence[i] != charSequence[length - i - 1]) {
            if (skipCharCount > 0) {
                when {
                    (charSequence[i] == charSequence[length - i - 2]) &&
                            (charSequence[i + 1] == charSequence[length - i - 1]) -> {
                        val subCharSequence1 = charSequence.subSequence(i, length - i - 1)
                        val subCharSequence2 = charSequence.subSequence(i + 1, length - i)

                        return isSubPalindrome(subCharSequence1, skipCharCount) or
                                isSubPalindrome(subCharSequence2, skipCharCount)
                    }
                    charSequence[i] == charSequence[length - i - 2] -> {
                        val subCharSequence = charSequence.subSequence(i, length - i - 1)
                        return isSubPalindrome(subCharSequence, skipCharCount)
                    }
                    charSequence[i + 1] == charSequence[length - i - 1] -> {
                        val subCharSequence = charSequence.subSequence(i + 1, length - i)
                        return isSubPalindrome(subCharSequence, skipCharCount)
                    }
                    else -> return false
                }
            }
            return false
        }
    }
    return true
}

/**
 * @return is palindrome within [charSequence] and [skipCharCount]
 *
 */
fun isSubPalindrome(charSequence: CharSequence, skipCharCount: Int): Boolean {
    return if (charSequence.isNotEmpty()) {
        val count = skipCharCount - 1
        isPalindrome(charSequence, count)
    } else {
        true
    }
}
```
