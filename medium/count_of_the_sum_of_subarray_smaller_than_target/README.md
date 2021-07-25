# Count of the Sum of Subarray Smaller than Target

## Materials
* [Solutions](Solutions.md)
* Related questions, [hard] [Kth Smallest Subarray Sum](/hard/Kth_smallest_subarray_sum/)

## Description
Given an integer array `nums` of length `N` and an integer `target`, return the number of the subarray whose summation is smaller than the target.

A **subarray** is defined as a **non-empty** contiguous sequence A **subarray** is defined as a **non-empty** contiguous sequence of elements in an array.<br>
A **subarray sum** is the sum of all elements in the subarray.<br>

### Constrains:
* <code>N == nums.length</code>
* <code>1 <= N <= 2 * 10<sup>4</sup></code>
* <code>1 <= nums[i] <= 5 * 10<sup>4</sup></code>
* <code>1 <= target <= 10<sup>9</sup></code>

### Example 1:
<pre>
<b>Inputs:</b> nums = [1, 2, 3, 4], target = 5
<b>Output:</b> 5
<b>Explanation:</b> The subarrays of the nums are:
- [1] with sum <ins>1</ins>
- [2] with sum <ins>2</ins>
- [3] with sum <ins>3</ins>
- [4] with sum <ins>4</ins>
- [1, 2] with sum <ins>3</ins>
- [2, 3] with sum 5
- [3, 4] with sum 7
- [1, 2, 3] with sum 6
- [2, 3, 4] with sum 9
- [1, 2, 3, 4] with sum 10

And there are 5 subarrays whose summation is smaller than the target.
</pre>

### Example 2:
<pre>
<b>Inputs:</b> nums = [1, 10, 7], target = 15
<b>Output:</b> 4
<b>Explanation:</b> The subarrays of the nums are:
- [1] with sum <ins>1</ins>
- [10] with sum <ins>10</ins>
- [7] with sum <ins>7</ins>
- [1, 10] with sum <ins>11</ins>
- [10, 7] with sum 17
- [1, 10, 7] with sum 18

And there are 4 subarrays whose summation is smaller than the target.
</pre>
