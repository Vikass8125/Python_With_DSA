# Remove Duplicates from a List

## Problem Statement
You are given a list of integers. Write a Python program that removes any duplicate elements from the list and returns a new list with only unique elements. The order of elements in the list should be maintained.

### Parameters:
- `lst` (List of integers): The list of integers from which duplicates should be removed.

### Returns:
- A list of integers where all duplicates have been removed, preserving the original order.

### Example:

#### Example 1:
**Input:**
```python
lst = [1, 2, 2, 3, 4, 4, 5]
```
**Output:**
```
[1, 2, 3, 4, 5]
```

#### Example 2:
**Input:**
```python
lst = [4, 5, 5, 4, 6, 7]
```
**Output:**
```
[4, 5, 6, 7]
```

---

## Explanation
The goal is to create a new list that contains only the unique elements from the original list while preserving their order of appearance. For example:
- In the first input, `[1, 2, 2, 3, 4, 4, 5]`, the unique elements are `[1, 2, 3, 4, 5]`.
- In the second input, `[4, 5, 5, 4, 6, 7]`, the unique elements are `[4, 5, 6, 7]`.

---

## Solution
We will approach the problem using a simple iteration and maintain a separate list to store unique elements.

### Brute Force Solution
In the brute force method, we iterate through each element of the input list and check if it is already present in the result list. If not, we add it to the result list.

### Implementation:
```python
def remove_duplicates(lst):
    unique_list = []
    for item in lst:
        # Check if the item is already in the unique_list
        if item not in unique_list:
            unique_list.append(item)
    return unique_list

# Example Usage:
lst = [1, 2, 2, 3, 4, 4, 5]
print(remove_duplicates(lst))  # Output: [1, 2, 3, 4, 5]
```

### Code Walkthrough
1. **Initialization**: Start with an empty list, `unique_list`, to store the unique elements.
2. **Iterate through the input list**: For each element:
   - Check if it is already present in `unique_list`.
   - If not, append it to `unique_list`.
3. **Return the result**: After processing all elements, return `unique_list` containing only unique elements.

---

### Optimal Solution
We can leverage Python's `set` data structure to achieve the same result more efficiently. However, since sets do not maintain order, we combine it with a manual iteration to ensure order preservation.

### Implementation:
```python
def remove_duplicates(lst):
    seen = set()
    unique_list = []
    for item in lst:
        if item not in seen:
            unique_list.append(item)
            seen.add(item)
    return unique_list

# Example Usage:
lst = [4, 5, 5, 4, 6, 7]
print(remove_duplicates(lst))  # Output: [4, 5, 6, 7]
```

### Code Walkthrough
1. **Initialize a set**: Use `seen` to keep track of elements that have already been encountered.
2. **Iterate through the list**: For each element:
   - Check if it is in `seen`.
   - If not, add it to `unique_list` and update `seen`.
3. **Return the result**: `unique_list` now contains unique elements in their original order.

---

## Complexity Analysis
### Brute Force Solution:
- **Time Complexity**: `O(n^2)` where `n` is the length of the list. For each element, we check if it is in `unique_list`, which takes `O(n)` in the worst case.
- **Space Complexity**: `O(n)` for the `unique_list`.

### Optimal Solution:
- **Time Complexity**: `O(n)` where `n` is the length of the list. We iterate through the list once, and set operations (add and check) are `O(1)`.
- **Space Complexity**: `O(n)` for the `unique_list` and `seen` set.

---

## Summary
The brute force solution is simple but inefficient for large lists due to its `O(n^2)` time complexity. The optimal solution, which combines a set for tracking and a list for maintaining order, is both efficient and concise, making it suitable for real-world applications.
