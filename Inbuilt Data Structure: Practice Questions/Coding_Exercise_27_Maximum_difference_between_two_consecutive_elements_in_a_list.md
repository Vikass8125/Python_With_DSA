# Maximum Difference Between Two Consecutive Elements in a List

## Problem Statement

You are given a list of integers. Write a Python program to find the **maximum difference** between two consecutive elements in the list using a **brute-force approach**. The difference is defined as the absolute value of the difference between two consecutive elements.

### Parameters:
- `lst` (List of integers): A list of integers.

### Returns:
- An integer representing the maximum difference between two consecutive elements.

---

## Examples:

### Example 1:
**Input:**
```python
lst = [1, 7, 3, 10, 5]
```
**Output:**
```python
7
```
**Explanation:**
The maximum difference is between `3` and `10` (i.e., `|3 - 10| = 7`).

### Example 2:
**Input:**
```python
lst = [10, 11, 15, 3]
```
**Output:**
```python
12
```
**Explanation:**
The maximum difference is between `15` and `3` (i.e., `|15 - 3| = 12`).

---

## Solution Approach

### Brute Force Approach
The brute-force solution involves iterating through the list to calculate the absolute difference between every pair of consecutive elements. The **maximum difference** is updated whenever a larger difference is found.

### Steps:
1. Check for an edge case: If the list has fewer than two elements, return `0` since no difference can be calculated.
2. Initialize a variable `max_diff` to store the maximum difference. Start with `0`.
3. Loop through the list starting from the second element.
   - For each element, calculate the absolute difference with the previous element.
   - Compare the difference with `max_diff` and update `max_diff` if the current difference is larger.
4. Return `max_diff` after completing the loop.

---

### Brute Force Code Implementation
```python
def max_consecutive_difference(lst):
    # Edge case: if the list is empty or has only one element, return 0
    if len(lst) < 2:
        return 0
    
    max_diff = 0  # Initialize max difference as 0
    
    # Iterate through the list to calculate consecutive differences
    for i in range(1, len(lst)):
        current_diff = abs(lst[i] - lst[i - 1])  # Calculate absolute difference
        if current_diff > max_diff:  # Update max_diff if current_diff is greater
            max_diff = current_diff
    
    return max_diff  # Return the maximum difference
```

---

### Code Walkthrough:
1. **Edge Case Handling:**
   - If the input list `lst` has fewer than 2 elements, it returns `0` as there are no consecutive elements to compare.

2. **Initialization:**
   - `max_diff` is initialized to `0`, representing the minimum possible difference.

3. **Iteration:**
   - The loop starts at index `1` and calculates the absolute difference between the current and previous elements (`|lst[i] - lst[i-1]|`).
   - If the current difference is larger than `max_diff`, `max_diff` is updated.

4. **Result:**
   - The function returns the largest difference found during the loop.

---

### Dry Run:
#### Input:
`lst = [1, 7, 3, 10, 5]`

#### Iteration Steps:
| Index | Current Element | Previous Element | Difference | Max Difference |
|-------|-----------------|------------------|------------|----------------|
| 1     | 7               | 1                | 6          | 6              |
| 2     | 3               | 7                | 4          | 6              |
| 3     | 10              | 3                | 7          | 7              |
| 4     | 5               | 10               | 5          | 7              |

**Output:** `7`

---

## Complexity Analysis:

1. **Time Complexity:**
   - The algorithm iterates through the list once, so the time complexity is **O(n)**, where `n` is the size of the list.

2. **Space Complexity:**
   - The algorithm uses only a few variables for computation, so the space complexity is **O(1)**.

