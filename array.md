# Array Interview Problems

## Easy Problems

1. **Two Sum**
   - Given an array of integers and a target sum, return indices of the two numbers that add up to the target.
   - Example: Input: [2, 7, 11, 15], target = 9
   - Output: [0, 1] (because 2 + 7 = 9)

2. **Remove Duplicates**
   - Remove duplicates from a sorted array in-place and return the new length.
   - Example: Input: [1, 1, 2, 2, 3]
   - Output: 3, with first three elements being 1, 2, 3

3. **Maximum Subarray**
   - Find the contiguous subarray with the largest sum.
   - Example: Input: [-2, 1, -3, 4, -1, 2, 1, -5, 4]
   - Output: 6 (subarray [4, -1, 2, 1])

4. **Plus One**
   - Given a non-empty array of digits representing an integer, increment one to the integer.
   - Example: Input: [1, 2, 3]
   - Output: [1, 2, 4]

5. **Move Zeroes**
   - Move all zeroes to the end of array while maintaining the relative order of non-zero elements.
   - Example: Input: [0, 1, 0, 3, 12]
   - Output: [1, 3, 12, 0, 0]

6. **Intersection of Two Arrays**
   - Find the intersection of two arrays.
   - Example: Input: nums1 = [1, 2, 2, 1], nums2 = [2, 2]
   - Output: [2]

7. **Contains Duplicate**
   - Determine if array contains any duplicate elements.
   - Example: Input: [1, 2, 3, 1]
   - Output: true

8. **Best Time to Buy and Sell Stock I**
   - Find the maximum profit by buying and selling once.
   - Example: Input: [7, 1, 5, 3, 6, 4]
   - Output: 5

9. **Missing Number**
   - Find the missing number in array containing n distinct numbers from 0 to n.
   - Example: Input: [3, 0, 1]
   - Output: 2

10. **Single Number**
    - Find the element that appears only once in array where others appear twice.
    - Example: Input: [2, 2, 1]
    - Output: 1

## Medium Problems

1. **3Sum**
   - Find all unique triplets in the array that sum up to zero.
   - Example: Input: [-1, 0, 1, 2, -1, -4]
   - Output: [[-1, -1, 2], [-1, 0, 1]]

2. **Container With Most Water**
   - Find two lines that together with x-axis forms a container that holds the most water.
   - Example: Input: [1, 8, 6, 2, 5, 4, 8, 3, 7]
   - Output: 49

3. **Product of Array Except Self**
   - Return array where each element is product of all other elements.
   - Example: Input: [1, 2, 3, 4]
   - Output: [24, 12, 8, 6]

4. **Subarray Sum Equals K**
   - Find total number of continuous subarrays whose sum equals k.
   - Example: Input: [1, 1, 1], k = 2
   - Output: 2

5. **Next Permutation**
   - Rearrange numbers into lexicographically next greater permutation.
   - Example: Input: [1, 2, 3]
   - Output: [1, 3, 2]

6. **Search in Rotated Sorted Array**
   - Search for target value in rotated sorted array.
   - Example: Input: nums = [4, 5, 6, 7, 0, 1, 2], target = 0
   - Output: 4

7. **Merge Intervals**
   - Merge all overlapping intervals.
   - Example: Input: [[1,3], [2,6], [8,10], [15,18]]
   - Output: [[1,6], [8,10], [15,18]]

8. **Find First and Last Position**
   - Find starting and ending position of given target value in sorted array.
   - Example: Input: nums = [5,7,7,8,8,10], target = 8
   - Output: [3,4]

9. **Jump Game**
   - Determine if you can reach the last index.
   - Example: Input: [2,3,1,1,4]
   - Output: true

10. **Rotate Array**
    - Rotate array to right by k steps.
    - Example: Input: [1,2,3,4,5,6,7], k = 3
    - Output: [5,6,7,1,2,3,4]

## Hard Problems

1. **First Missing Positive**
   - Find smallest missing positive integer in unsorted array.
   - Example: Input: [3,4,-1,1]
   - Output: 2

2. **Trapping Rain Water**
   - Calculate how much water can be trapped between bars.
   - Example: Input: [0,1,0,2,1,0,1,3,2,1,2,1]
   - Output: 6

3. **Median of Two Sorted Arrays**
   - Find median of two sorted arrays.
   - Example: Input: nums1 = [1,3], nums2 = [2]
   - Output: 2.0

4. **Maximum Rectangle**
   - Find largest rectangle containing only 1's in binary matrix.
   - Example: Input: [[1,0,1,0,0],[1,0,1,1,1],[1,1,1,1,1],[1,0,0,1,0]]
   - Output: 6

5. **Sliding Window Maximum**
   - Find maximum element in sliding window.
   - Example: Input: nums = [1,3,-1,-3,5,3,6,7], k = 3
   - Output: [3,3,5,5,6,7]

6. **Array of Doubled Pairs**
   - Check if array can be arranged into pairs where one element is double of other.
   - Example: Input: [4,-2,2,-4]
   - Output: true

7. **Maximum Sum of 3 Non-Overlapping Subarrays**
   - Find three non-overlapping subarrays with maximum sum.
   - Example: Input: [1,2,1,2,6,7,5,1], k = 2
   - Output: [0,3,5]

8. **Maximum Frequency Stack**
   - Implement FreqStack that supports push and pop operations.
   - Example: Push sequence: [5,7,5,7,4,5]
   - Pop sequence should return: [5,7,5]

9. **Count of Smaller Numbers After Self**
   - Count smaller elements on right side for each element.
   - Example: Input: [5,2,6,1]
   - Output: [2,1,1,0]

10. **Best Time to Buy and Sell Stock III**
    - Maximum profit with at most two transactions.
    - Example: Input: [3,3,5,0,0,3,1,4]
    - Output: 6