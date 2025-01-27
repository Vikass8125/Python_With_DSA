# Coding Exercise 35: Check if List is Subset of Another List

## Problem Statement

You are given two lists of integers. Write a Python program that checks whether the first list is a subset of the second list using a brute-force approach, without using the `in` keyword. A list is considered a subset if all elements of the first list are present in the second list.

### Parameters:
- `lst1` (List of integers): The first list, which is being checked as a subset.
- `lst2` (List of integers): The second list, which is the list to compare against.

### Returns:
- A boolean value: `True` if `lst1` is a subset of `lst2`, otherwise `False`.

---

## Examples

### Example 1:
**Input:**
```python
lst1 = [1, 2, 3]
lst2 = [1, 2, 3, 4, 5]
```
**Output:**
```python
True
```
**Explanation:**
- All elements in `lst1` are present in `lst2`, so it is a subset.

### Example 2:
**Input:**
```python
lst1 = [1, 6]
lst2 = [1, 2, 3, 4, 5]
```
**Output:**
```python
False
```
**Explanation:**
- The element `6` is not present in `lst2`, so `lst1` is not a subset of `lst2`.

---

## Solution Approach

### Steps to Solve:
1. **Iterate Through `lst1`:**
   - For each element in `lst1`, check if it exists in `lst2`.
2. **Flag for Existence:**
   - Use a flag variable (`found`) to determine if the current element from `lst1` exists in `lst2`.
3. **Return Result:**
   - If any element in `lst1` is not found in `lst2`, return `False` immediately.
   - If all elements are found, return `True`.

---

### Code Implementation
```python
def is_subset(lst1, lst2):
    """
    Function to check if one list is a subset of another using brute force.

    Parameters:
    lst1 (list): The list to check as a subset.
    lst2 (list): The list to compare against.

    Returns:
    bool: True if lst1 is a subset of lst2, False otherwise.
    """
    # Iterate through each element of lst1
    for element in lst1:
        found = False  # Flag to check if element is found in lst2
        # Check each element of lst2
        for item in lst2:
            if item == element:  # Compare each element
                found = True
                break
        if not found:  # If any element from lst1 is not found in lst2, return False
            return False
    return True  # If all elements in lst1 are found, return True
```

---

### Code Walkthrough
1. **Outer Loop:**
   - Iterate through each element in `lst1`.
2. **Inner Loop:**
   - Compare the current element of `lst1` with every element in `lst2`.
   - If a match is found, set `found = True` and exit the inner loop.
3. **Check for Missing Elements:**
   - If `found` remains `False` after the inner loop, return `False` immediately.
4. **Final Check:**
   - If all elements in `lst1` are found, return `True`.

---

### Dry Run
#### Input:
`lst1 = [1, 2, 3]`, `lst2 = [1, 2, 3, 4, 5]`

#### Execution Steps:
| Step | Element from `lst1` | Compared Elements in `lst2` | Found? | Result |
|------|----------------------|----------------------------|--------|--------|
| 1    | 1                    | [1, 2, 3, 4, 5]           | True   | Continue|
| 2    | 2                    | [1, 2, 3, 4, 5]           | True   | Continue|
| 3    | 3                    | [1, 2, 3, 4, 5]           | True   | Return True |

#### Output:
`True`

---

### Complexity Analysis

1. **Time Complexity:**
   - \( O(n \cdot m) \), where \( n \) is the length of `lst1` and \( m \) is the length of `lst2`.
   - For each element in `lst1`, we iterate through all elements in `lst2`.

2. **Space Complexity:**
   - \( O(1) \), as no additional space is used.

---

### Usage
This function is useful for scenarios such as:
- Validating subsets in mathematical computations.
- Checking permissions in lists of roles or features.

### Example Usage:
```python
# Example 1
print(is_subset([1, 2, 3], [1, 2, 3, 4, 5]))  # Output: True

# Example 2
print(is_subset([1, 6], [1, 2, 3, 4, 5]))  # Output: False

# Example 3
print(is_subset([], [1, 2, 3, 4, 5]))  # Output: True

# Example 4
print(is_subset([1, 2, 3], []))  # Output: False
```

---

Happy coding! 😊
