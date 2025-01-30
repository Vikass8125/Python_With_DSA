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

---
---
# Coding Exercise: Binary Search Algorithm

## Problem Description

You are given a sorted list of integers and a target value. Implement a function to perform a **Binary Search** on the list to determine if the target exists and return its index. If the target is not found, return `-1`.

Binary Search works by repeatedly dividing the search space in half, reducing the time complexity significantly compared to linear search.

## Parameters:
- `arr` (List of integers): A sorted list of integers.
- `target` (Integer): The value to search for.

## Returns:
- The index of the target if found (0-based index), otherwise `-1`.

---

## Example:

```python
# Example 1
Input: arr = [1, 3, 5, 7, 9, 11], target = 5
Output: 2  # (5 is at index 2)

# Example 2
Input: arr = [2, 4, 6, 8, 10], target = 7
Output: -1  # (7 is not in the list)
```

---

## **Pseudo Code**:

```
1. Initialize low = 0 and high = length(arr) - 1
2. While low <= high:
   a. Compute mid = (low + high) // 2
   b. If arr[mid] == target, return mid
   c. If arr[mid] < target, search the right half (low = mid + 1)
   d. If arr[mid] > target, search the left half (high = mid - 1)
3. If target is not found, return -1
```

---

## **Python Implementation**:

```python
def binary_search(arr, target):
    """
    Function to perform binary search on a sorted list.
    
    Parameters:
    arr (list): Sorted list of integers.
    target (int): The value to search for.
    
    Returns:
    int: Index of target if found, otherwise -1.
    """
    low, high = 0, len(arr) - 1
    
    while low <= high:
        mid = (low + high) // 2  # Find middle index
        
        if arr[mid] == target:
            return mid  # Target found
        elif arr[mid] < target:
            low = mid + 1  # Search right half
        else:
            high = mid - 1  # Search left half
    
    return -1  # Target not found

# Example usage:
print(binary_search([1, 3, 5, 7, 9, 11], 5))  # Output: 2
print(binary_search([2, 4, 6, 8, 10], 7))     # Output: -1
```

---

## **Time Complexity Analysis**:

- **Best Case**: `O(1)` (When the target is found at the middle index initially).
- **Average Case**: `O(log n)` (Each iteration halves the search space).
- **Worst Case**: `O(log n)` (When the target is not in the list, leading to full depth search).

---

## **Advantages of Binary Search**:
✅ Much faster than Linear Search (`O(n)`) for large datasets.
✅ Works efficiently on large sorted datasets.
✅ Can be implemented iteratively or recursively.

---

## **Limitations**:
❌ Requires a sorted list as input.
❌ Not efficient for small lists compared to simple searches.
❌ Doesn't work well on dynamically changing data.

---

## **Alternate Approach: Recursive Binary Search**:

```python
def recursive_binary_search(arr, target, low, high):
    if low > high:
        return -1  # Target not found
    
    mid = (low + high) // 2
    if arr[mid] == target:
        return mid
    elif arr[mid] < target:
        return recursive_binary_search(arr, target, mid + 1, high)
    else:
        return recursive_binary_search(arr, target, low, mid - 1)

# Example usage:
arr = [1, 3, 5, 7, 9, 11]
target = 5
print(recursive_binary_search(arr, target, 0, len(arr) - 1))  # Output: 2
```

---

## **Conclusion**
Binary Search is an efficient searching technique that works best on sorted lists. It reduces the search space by half in each iteration, making it significantly faster than linear search for large datasets.

---

