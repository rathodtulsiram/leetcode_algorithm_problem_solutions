# [Two Sum](https://leetcode.com/problems/two-sum/)

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:

Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].

# Solution
/**
* @return array with input [nums] & [target]
*/
fun twoSum(nums: IntArray, target: Int): IntArray {
        val size = nums.size
         for(i in 0 until size){
             for(j in i + 1 until size){
                 if(nums[i] + nums[j] == target){
                     val arr = IntArray(2)
                     arr[0] = i
                     arr[1] = j
                     return arr
                 }
            }
         }
        return IntArray(1)
    }
