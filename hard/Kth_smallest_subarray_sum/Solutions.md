# Solutions
## Best Solution: binary search, sliding window with presum
**Time Complexity:** O(*N* * log(sum(nums)))<br>
**Space Complexity:** O(*N*)

```python
def solve(nums, K):
    ans = 0
    N = len(nums)

    # calculate the presum of the nums
    presum = [0]
    for i in range(N):
        presum.append(presum[-1] + nums[i])

    def check(target):
        # sliding window
        cnt = 0
        l, r = 0, 0
        for r in range(len(presum)):
            curr_sum = presum[r] - presum[l]
            while curr_sum > target:
                l += 1
                curr_sum = presum[r] - presum[l]
            cnt += r - l

        # There is $cnt subarrays whose sum is smaller or equal than the target,
        # and check if $cnt smaller than K
        return cnt < K

    # binary search
    l, r = 0, sum(nums)
    while l < r:
        mid = (l + r) // 2
        if check(mid):
            l = mid + 1
        else:
            r = mid

    return l

```

## Better Solution: calcuate all the subarray with presum and sort
**Time Complexity:** O(*N*<sup>2</sup> + *N*<sup>2</sup>log(*N*<sup>2</sup>))<br>
**Space Complexity:** O(*N*<sup>2</sup>)

```python
def solve(nums, K):
    N = len(nums)

    # calculate the presum of the nums
    presum = [0]
    for i in range(N):
        presum.append(presum[-1] + nums[i])

    # calculate all the subarrays
    all_subarrays_sum = []
    for i in range(N):
        for j in range(i + 1, N + 1, 1):
            curr_sum = presum[j] - presum[i]
            all_subarrays_sum.append(curr_sum)

    all_subarrays_sum.sort()
    return all_subarrays_sum[K - 1]
```

## Brute force Solution: calcuate all the subarray without presum and sort
**Time Complexity:** O(*N*<sup>3</sup> + *N*<sup>2</sup>log(*N*<sup>2</sup>))<br>
**Space Complexity:** O(*N*<sup>2</sup>)

```python
def solve(nums, K):
    N = len(nums)

    # calculate all the subarrays
    all_subarrays_sum = []
    for i in range(N):
        for j in range(i, N, 1):
            curr_sum = 0
            for k in range(i, j + 1, 1):
                curr_sum += nums[k]
            all_subarrays_sum.append(curr_sum)

    all_subarrays_sum.sort()
    return all_subarrays_sum[K - 1]
```
