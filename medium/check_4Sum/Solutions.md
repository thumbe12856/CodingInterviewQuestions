# Solutions
## Best Solution:
**Time Complexity:** O(min(*N*<sup>2</sup>, max(nums) * 2 * 4))<br>
**Space Complexity:** O(1)

```python
def solve(nums):
    N = len(nums)
    vis = {}
    for i in range(N):
        for j in range(i):
            val = nums[i] + nums[j]
            if val in vis:
                x, y = vis[val]
                if len(set([i, j, x, y])) == 4:
                    return True
            else:
                vis[val] = (i, j)
    return False
```

## Better Solution: copy idea from 3Sum
**Time Complexity:** O(*N*log*N* + *N*<sup>3</sup>)<br>
**Space Complexity:** O(1)

```python
def solve(nums):
    N = len(nums)
    nums.sort()

    for i in range(N):
        for j in range(i + 1, N, 1):
            l, r = j + 1, N - 1
            target = nums[i] + nums[j]
            while l < r:
                curr_val = nums[l] + nums[r]
                if curr_val == target:
                    return True
                elif curr_val < target:
                    l += 1
                else:
                    r -= 1

    return False
```

## Brute force Solution: calcuate all the pairs
**Time Complexity:** O(*N*<sup>4</sup>)<br>
**Space Complexity:** O(1)

```python
def solve(nums, target):
    N = len(nums)
    for i in range(N):
        for j in range(i + 1, N, 1):
            for x in range(j + 1, N, 1):
                for y in range(x + 1, N, 1):
                    if nums[i] + nums[j] == nums[x] + nums[y]:
                        return True
    return False
```
