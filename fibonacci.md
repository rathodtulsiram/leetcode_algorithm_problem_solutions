# [Fibonacci Number](https://leetcode.com/problems/fibonacci-number/)

The Fibonacci numbers, commonly denoted F(n) form a sequence, called the Fibonacci sequence, such that each number is the sum of the two preceding ones, starting from 0 and 1. That is,

F(0) = 0,   F(1) = 1
F(N) = F(N - 1) + F(N - 2), for N > 1.
Given N, calculate F(N).

# Solution
```
/**
* @return fiboncci number at [N] position
*/
fun fib(N: Int): Int {
        var start = 0
        var next = 1
        var num = 0
       
       return when(N){
            0 -> return num
            1 -> return start + next
            else ->{
                for(i in 1 until N){
                    num = start + next
                    start = next
                    next = num
                }
                num
            }
        }
      }
```
