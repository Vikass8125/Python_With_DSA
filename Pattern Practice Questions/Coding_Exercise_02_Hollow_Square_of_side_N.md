# Coding Exercise 2: Hollow Square of side 'N'

## Problem Description
You are given an integer `n`. Your task is to return a hollow square pattern of size `n x n` made up of the character `*`, represented as a list of strings. The hollow square has `*` on the border and spaces ` ` in the middle (except for side lengths of 1 and 2).

---

## Input Parameters
- `n (int)`: The size of the square (number of rows and columns).

---

## Output
A list of strings where each string is a row of `n` characters, representing a hollow square.

---

## Examples

### Example 1:
**Input:**
```
n = 3
```
**Output:**
```
['***', '* *', '***']
```

### Example 2:
**Input:**
```
n = 5
```
**Output:**
```
['*****', '*   *', '*   *', '*   *', '*****']
```

### Example 3:
**Input:**
```
n = 1
```
**Output:**
```
['*']
```

---

## Solution Explanation

### Brute Force Approach
1. **Special Cases:**
   - If `n = 1`, the square is a single `*`. Return `['*']`.
   - If `n = 2`, the square is fully filled with `*`. Return `['**', '**']`.

2. **General Case:**
   - Initialize an empty list `square` to store the rows of the pattern.
   - The first and last rows are fully filled with `*`. Add them to the list.
   - For the rows in between:
     - Place `*` at the start and end of the row.
     - Fill the middle part of the row with spaces (`n - 2` spaces).
     - Append this row to the list.
   - Return the final list.

---

### Code for Brute Force Approach
```python
def generate_hollow_square(n):
    """
    Function to return a hollow square pattern of '*' of side n as a list of strings.
    
    Parameters:
    n (int): The size of the square.
    
    Returns:
    list: A list of strings where each string represents a row of the hollow square.
    """
    # Initialize an empty list to store the rows of the hollow square
    square = []
    
    # Handle the case when n is 1 separately
    if n == 1:
        return ['*']
    
    # The first and last rows are full of '*'
    square.append('*' * n)  # First row
    
    # For the middle rows, the first and last characters are '*', rest are spaces
    for i in range(n - 2):
        square.append('*' + ' ' * (n - 2) + '*')
    
    # The last row is also full of '*'
    square.append('*' * n)  # Last row
    
    # Return the list of rows
    return square

# Example Usage
print(generate_hollow_square(3))  # Output: ['***', '* *', '***']
print(generate_hollow_square(5))  # Output: ['*****', '*   *', '*   *', '*   *', '*****']
print(generate_hollow_square(1))  # Output: ['*']
```

---

### Optimal Solution
This problem does not have significant room for optimization as the brute force approach is already efficient.

#### Complexity Analysis
- **Time Complexity:**
  - Constructing each row involves either creating a string of length `n` (first and last rows) or inserting `n-2` spaces (middle rows).
  - This results in an overall complexity of **O(n)**.

- **Space Complexity:**
  - The additional space used is only for the output list, which is required to store the `n` rows of the square.
  - Therefore, the space complexity is **O(n)**.

---

### Final Notes
Understanding how to create hollow shapes lays a foundation for generating more intricate patterns. Practice modifying this logic to handle other shapes like hollow triangles or diamonds!
