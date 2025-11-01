# Leetcode Two Sum

**Platform:** Leetcode  
**Difficulty:** Easy  
**Tags:** Array, Hash Table

Given an array of integers `nums` and an integer `target`, return
indices of the two numbers such that they add up to `target`.

You may assume that each input would have exactly one solution, and you
may not use the same element twice. You can return the answer in any
order.

**Example 1:**  
Input: nums = \[2,7,11,15\], target = 9  
Output: \[0,1\]  
Explanation: Because nums\[0\] + nums\[1\] == 9, we return \[0, 1\].

**Example 2:**  
Input: nums = \[3,2,4\], target = 6  
Output: \[1,2\]

**Example 3:**  
Input: nums = \[3,3\], target = 6  
Output: \[0,1\]

- $2 \leq \text{nums.length} \leq 10^4$

- $-10^9 \leq \text{nums[i]} \leq 10^9$

- $-10^9 \leq \text{target} \leq 10^9$

- Only one valid answer exists

**Follow-up:** Can you come up with an algorithm that is less than
$O(n^2)$ time complexity?

``` c
#include <stdio.h>
#include <stdlib.h>

int* twoSum(int* nums, int numsSize, int target, int* returnSize) {
    for (int i = 0; i < numsSize; i++){
        for (int j = i + 1; j < numsSize; j++){
            if(nums[i] + nums[j] == target){
                int* result = (int*)malloc(2*sizeof(int));
                *returnSize = 2;
                result[0] = i;
                result[1] = j;
                return result;
            }
        }
    }
    *returnSize = 0;
    return NULL;
}
```

**Time Complexity:** $O(n^2)$ — nested loops iterate over all pairs.  
**Space Complexity:** $O(1)$ — only constant extra space used (ignoring
output array).

- Brute-force works for small arrays, but follow-up requires using a
  hash map for $O(n)$ solution.

- Always read constraints carefully — input size determines whether
  $O(n^2)$ is feasible.

- Separating approach, code, and lessons makes reviewing problems much
  faster.
