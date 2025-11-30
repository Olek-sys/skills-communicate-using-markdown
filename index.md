
# This is my first communicate using Markdown

## I want to become a Data sientist and data engineere. I hope I do it! 

### I make a commitment to put forth my best effort to make it real 

##### Kozak Olekasndr date: 2025.11.30 
### Here is an image :) 
![Image of Yaktocat](https://octodex.github.com/images/yaktocat.png)

## My leetcode task solution
### Make sum divisible by P
```
class Solution(object):
    def minSubarray(self, nums, p):
        total_sum = sum(nums)
        target = total_sum % p

        if total_sum % p == 0:
            return 0

        mod_map = {0 : -1 }

        current_sum = 0
        min_len = len(nums) 

        for i, num in enumerate(nums):
            current_sum += num
            current_mod = current_sum % p

            needed = (current_mod - target + p) % p

            if needed in mod_map:
                prev_index = mod_map[needed]
                current_len = i - prev_index

                min_len = min(min_len, current_len)
            
            mod_map[current_mod] = i

        if min_len < len(nums):
            return min_len
        else:
            return -1
```

