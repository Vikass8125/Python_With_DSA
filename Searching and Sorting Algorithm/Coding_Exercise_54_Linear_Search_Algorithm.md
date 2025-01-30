# Coding Exercise 54: Linear Search Algorithm

## Problem Description

### Title: Linear Search in a List

**Description:** Implement a function `linear_search` that performs a linear search on a list to find a given value. The function should return the index of the first occurrence of the value in the list, or `-1` if the value is not found.

### Parameters:
- `arr` (list): A list of elements (can be empty).
- `target` (any): The value to search for in the list.

### Return:
- The index of the first occurrence of the `target` value (0-based), or `-1` if not found.

---

## Examples

```python
linear_search([3, 7, 2, 5], 2)  # Output: 2
linear_search([1, 1, 2, 1], 1)  # Output: 0
linear_search([], 5)            # Output: -1
linear_search([4, 2, 8], 6)     # Output: -1
```

---

## Solution

### Approach:
- Iterate through each element of the list using a loop.
- Compare each element with the target value.
- If a match is found, return the current index.
- If the loop completes without finding a match, return `-1`.

### Implementation

```python
def linear_search(arr, target):
    """
    Perform a linear search to find the first occurrence of target in arr.
    
    Parameters:
    arr (list): The list of elements.
    target (any): The value to search for.
    
    Returns:
    int: The index of the first occurrence of target, or -1 if not found.
    """
    for i in range(len(arr)):
        if arr[i] == target:
            return i
    return -1

# Example usage:
print(linear_search([3, 7, 2, 5], 2))  # Output: 2
print(linear_search([1, 1, 2, 1], 1))  # Output: 0
print(linear_search([], 5))            # Output: -1
print(linear_search([4, 2, 8], 6))     # Output: -1
```

---

## Complexity Analysis
- **Time Complexity:** `O(n)`, where `n` is the length of the list. This is because, in the worst case, we may need to iterate through all elements.
- **Space Complexity:** `O(1)`, since no extra space is used apart from a few variables.

---

## Edge Cases Considered
- An empty list.
- The target appears multiple times in the list (ensures first occurrence is returned).
- The target does not exist in the list.
- A list with only one element.

---

## Alternative Approach using `enumerate`

```python
def linear_search(arr, target):
    for index, value in enumerate(arr):
        if value == target:
            return index
    return -1
```

This approach simplifies indexing by using `enumerate()`, making the code more readable.
