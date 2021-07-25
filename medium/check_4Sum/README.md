# Check 4Sum

## Materials
* reference: https://codeforces.com/problemset/problem/1500/A
* [Solutions](Solutions.md)

## Description
Given an integer array `nums` of length `N`.<br>
Check if there exist a pair that <code>nums[i] + nums[j] = nums[x] + nums[y]</code>, where <code>i, j, x, y</code> are unique.


### Constrains:
* <code>N == nums.length</code>
* <code>1 <= N <= 2 * 10<sup>5</sup></code>
* <code>1 <= nums[i] <= 2.5 * 10<sup>6</sup></code>

### Example 1:
<pre>
<b>Inputs:</b> nums = [2, 1, 5, 2, 7, 4]
<b>Output:</b> True
<b>Explanation:</b>
nums[1] + nums[2] = 1 + 5 = 2 + 4 = nums[0] + nums[5]
</pre>

### Example 2:
<pre>
<b>Inputs:</b> nums = [1, 3, 1, 9, 20]
<b>Output:</b> False
<b>Explanation:</b> There is no pair match the condition.
</pre>
