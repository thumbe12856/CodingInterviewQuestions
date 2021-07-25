# Solutions
## Best Solution: Sliding Window with presum
**Time Complexity:** O(*N*)<br>
**Space Complexity:** O(*N*)

```python
def solve(nums, target):
    ans = 0
    N = len(nums)

    # calculate the presum of the nums
    presum = [0]
    for i in range(N):
        presum.append(presum[-1] + nums[i])

    # sliding window
    l, r = 0, 0
    for r in range(1, N + 1, 1):
        curr_sum = presum[r] - presum[l]
        while curr_sum >= target:
            l += 1
            curr_sum = presum[r] - presum[l]
        ans += r - l

    return ans
```

## Better Solution: calcuate all the subarray with presum
**Time Complexity:** O(*N*<sup>2</sup>)<br>
**Space Complexity:** O(*N*)

```python
def solve(nums, target):
    ans = 0
    N = len(nums)

    # calculate the presum of the nums
    presum = [0]
    for i in range(N):
        presum.append(presum[-1] + nums[i])

    # calculate all the subarrays
    for i in range(N):
        for j in range(i + 1, N + 1, 1):
            curr_sum = presum[j] - presum[i]
            if curr_sum < target:
                ans += 1

    return ans
```

## Brute force Solution: calcuate all the subarray without presum
**Time Complexity:** O(*N*<sup>3</sup>)<br>
**Space Complexity:** O(1)

```python
def solve(nums, target):
    ans = 0
    N = len(nums)

    # calculate all the subarrays
    for i in range(N):
        for j in range(i, N, 1):
            curr_sum = 0
            for k in range(i, j + 1, 1):
                curr_sum += nums[k]

            if curr_sum < target:
                ans += 1

    return ans
```
