# Leetcode-283.-Move-Zeroes
# Description
Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.
# Solution
In the given problem we have been given an array nums which contains of integer values , we have to reform the array in such a way that all the non -zero number should be placed at the left of all 0's.

Example 1:

Input: nums = [0,1,0,3,12]

Output: [1,3,12,0,0]

Example 2:

Input: nums = [0]

Output: [0]
# Algorithm
1. Create a pointer insert ,  where the next non-zero element will be placed.
2. Loop through each number in nums array , and check if the number is a non zero element .
3. If it is not a zero then swap the current non-zero element (nums[i]) with the element at position insert.
4. Then move insert forward by on
# Code
class Solution:

    def moveZeroes(self, nums: List[int]) -> None:
        insert=0
        for i in range(len(nums)):
            if nums[i]!=0:
                nums[insert],nums[i]=nums[i],nums[insert]
                insert+=1
# Complexity
Time Complexity:

The loop runs exactly n times, where n is the length of nums.

Each iteration does a constant-time check (nums[i] != 0) and possibly a swap (which is O(1)).

No nested loops or extra passes.

Time Complexity: O(n)

Space Complexity:

Only one extra variable (insert) is used.

The operation is in-place — no additional data structures are created.

Space Complexity: O(1)
