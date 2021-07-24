# Kth Smallest Subarray Sum

## Materials
* reference: https://leetcode.com/problems/kth-smallest-subarray-sum/
* [Solutions](Solutions.md)
* Related questions, [medium] [Count of the Sum of Subarray Smaller than Target](/medium/count_of_the_sum_of_subarray_smaller_than_target/)

## Description
Given an integer array `nums` of length `N` and an integer `K`, return the <code>k<sup>th</sup></code> **smallest subarray sum**.

A **subarray** is defined as a **non-empty** contiguous sequence of elements in an array.<br>
A **subarray sum** is the sum of all elements in the subarray.<br>

### Constrains:
* <code>N == nums.length</code>
* <code>1 <= N <= 2 * 10<sup>4</sup></code>
* <code>1 <= nums[i] <= 5 * 10<sup>4</sup></code>
* <code>1 <= K <= N * (N + 1) / 2</code>

### Example 1:
<pre>
<b>Inputs:</b> nums = [1, 2, 3, 4], K = 5
<b>Output:</b> 5
<b>Explanation:</b> The subarrays of the nums are:
- [1] with sum 1
- [2] with sum 2
- [3] with sum 3
- [4] with sum 4
- [1, 2] with sum 3
- [2, 3] with sum 5
- [3, 4] with sum 7
- [1, 2, 3] with sum 6
- [2, 3, 4] with sum 9
- [1, 2, 3, 4] with sum 10

Ordering the sums from smallest to largest gives 1, 2, 3, 3, <ins>4</ins>, 5, 6, 7, 9, 10.
And the 5th smallest is 4.
</pre>

### Example 2:
<pre>
<b>Inputs:</b> nums = [1, 10, 7], K = 3
<b>Output:</b> 4
<b>Explanation:</b> The subarrays of the nums are:
- [1] with sum 1
- [10] with sum 10
- [7] with sum 7
- [1, 10] with sum 11
- [10, 7] with sum 17
- [1, 10, 7] with sum 18

Ordering the sums from smallest to largest gives 1, 7, <ins>10</ins>, 11, 17, 18.
And the 3rd smallest is 10.
</pre>
