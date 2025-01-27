# Coding Exercise 33: Palindromic Tuple

## Problem Statement

Design a Python function named `is_palindromic_tuple` to check if a tuple is palindromic, meaning it reads the same forwards and backwards.

### Parameters:
- `tup` (tuple): The input tuple that you need to check for palindromic property.

### Returns:
- `True` if the tuple is palindromic, `False` otherwise.

---

## Examples

### Example 1:
**Input:**
```python
tup = (1, 2, 3, 2, 1)
```
**Output:**
```python
True
```
**Explanation:**
- The tuple reads the same forwards `(1, 2, 3, 2, 1)` and backwards `(1, 2, 3, 2, 1)`, so it is palindromic.

### Example 2:
**Input:**
```python
tup = ('a', 'b', 'c', 'b', 'a')
```
**Output:**
```python
True
```
**Explanation:**
- The tuple reads the same forwards `('a', 'b', 'c', 'b', 'a')` and backwards `('a', 'b', 'c', 'b', 'a')`, so it is palindromic.

### Example 3:
**Input:**
```python
tup = (1, 2, 3, 4, 5)
```
**Output:**
```python
False
```
**Explanation:**
- The tuple reads `(1, 2, 3, 4, 5)` forwards but `(5, 4, 3, 2, 1)` backwards, so it is not palindromic.

### Example 4:
**Input:**
```python
tup = ('x', 'y', 'z', 'x')
```
**Output:**
```python
False
```
**Explanation:**
- The tuple reads `('x', 'y', 'z', 'x')` forwards but `('x', 'z', 'y', 'x')` backwards, so it is not palindromic.

### Example 5:
**Input:**
```python
tup = ('a',)
```
**Output:**
```python
True
```
**Explanation:**
- A single-element tuple reads the same forwards and backwards, so it is palindromic.

---

## Solution Approach

### Steps to Solve:
1. **Initialize Pointers:**
   - Use two pointers: `start` at the beginning of the tuple and `end` at the last element.
2. **Iterate Towards the Center:**
   - While `start` is less than or equal to `end`, check if the elements at `start` and `end` are equal.
   - If any pair of elements is not equal, return `False`.
3. **Return Result:**
   - If all pairs of elements match, return `True`.

---

### Code Implementation
```python
def is_palindromic_tuple(tup):
    """
    Function to check if a tuple is palindromic.

    Parameters:
    tup (tuple): The input tuple.

    Returns:
    bool: True if the tuple is palindromic, False otherwise.
    """
    # Initialize pointers for the start and end of the tuple
    start = 0
    end = len(tup) - 1

    # Loop until the start pointer is less than or equal to the end pointer
    while start <= end:
        # If elements at start and end pointers are not equal, it's not a palindrome
        if tup[start] != tup[end]:
            return False
        # Move the pointers towards the center
        start += 1
        end -= 1

    # If all elements matched, it is a palindrome
    return True
```

---

### Code Walkthrough
1. **Initialization:**
   - Set `start = 0` and `end = len(tup) - 1` to mark the first and last elements of the tuple.
2. **Iterate Through the Tuple:**
   - Compare elements at the `start` and `end` positions.
   - If they differ, return `False` immediately.
   - Otherwise, move `start` and `end` towards the center.
3. **Return Result:**
   - If no mismatch is found, return `True`.

---

### Dry Run
#### Input:
`tup = (1, 2, 3, 2, 1)`

#### Execution Steps:
| Step | Start Pointer | End Pointer | Compared Values | Result |
|------|---------------|-------------|-----------------|--------|
| 1    | 0             | 4           | 1 == 1          | Match  |
| 2    | 1             | 3           | 2 == 2          | Match  |
| 3    | 2             | 2           | 3 == 3          | Match  |
| 4    | -             | -           | -               | Palindrome |

**Output:** `True`

---

### Complexity Analysis

1. **Time Complexity:**
   - \( O(n) \), where \( n \) is the length of the tuple. Each element is checked at most once.

2. **Space Complexity:**
   - \( O(1) \), as no additional space is used apart from a few variables.

---

### Usage
This function can be used to:
- Validate palindromic sequences in data.
- Solve problems involving symmetrical patterns.

### Example Usage:
```python
# Example 1
print(is_palindromic_tuple((1, 2, 3, 2, 1)))  # Output: True

# Example 2
print(is_palindromic_tuple(('a', 'b', 'c', 'b', 'a')))  # Output: True

# Example 3
print(is_palindromic_tuple((1, 2, 3, 4, 5)))  # Output: False
```

---

Happy coding! 😊
