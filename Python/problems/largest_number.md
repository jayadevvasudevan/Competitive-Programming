Largest number

Problem description:
Given a list of non-negative integers nums, arrange them such that they form the largest number.
Note: The result may be very large, so you need to return a string instead of an integer.

Example test cases:

Example 1:
Input: nums = [10,2]
Output: "210"

Example 2:
Input: nums = [3,30,34,5,9]
Output: "9534330"

Example 3:
Input: nums = [1]
Output: "1"

Example 4:
Input: nums = [10]
Output: "10"
 
Constraints:

1 <= nums.length <= 100
0 <= nums[i] <= 109

Solution using Python:

        def largestNumber(nums: List[int]) -> str:
            if not nums: return ''
            for i in range(len(nums)):
                for j in range(i+1,len(nums)):
                    if int(str(nums[i])+str(nums[j])) < int(str(nums[j])+str(nums[i])):
                        nums[i], nums[j]= nums[j], nums[i]
            if nums[0]==0: return '0'
            for i in range(len(nums)):
                nums[i] = str(nums[i]) 
            return ''.join(nums)

Explanation of code:
1. If there are no elements in nums list, we return null string.
2. We need to loop through the list to position the elements.
3. If after arranging, the first element is 0, it means that the list contains n no. of 0s, so we return only '0'
4. The result is obtained by joining all the numbers is returned in string format.