# Coding Exercise 4: Right-Angled Triangle

## Problem Description
You are given an integer `n`. Your task is to return a right-angled triangle pattern of `*` where each side has `n` characters, represented as a list of strings. The triangle has `*` characters, starting with 1 star in the first row, 2 stars in the second row, and so on until the last row has `n` stars.

---

## Input Parameters
- `n (int)`: The height and base of the right-angled triangle.

---

## Output
A list of strings where each string is a row of `*` characters that increases in length from 1 to `n`.

---

## Examples

### Example 1:
**Input:**
```
n = 3
```
**Output:**
```
['*', '**', '***']
```

### Example 2:
**Input:**
```
n = 5
```
**Output:**
```
['*', '**', '***', '****', '*****']
```

---

## Solution Explanation

### Approach
1. **Understand the Pattern:**
   - The first row contains 1 `*`.
   - The second row contains 2 `*`.
   - This continues until the `n`th row, which contains `n` `*`.

2. **Steps to Solve:**
   - Initialize an empty list `triangle` to store the rows.
   - Use a loop that iterates from 1 to `n` (inclusive):
     - In each iteration, create a string of `i` stars (`'*' * i`) where `i` is the current row number.
     - Append this string to the list `triangle`.
   - Return the list containing all rows.

---

### Code
```python
def generate_triangle(n):
    """
    Function to return a right-angled triangle of '*' of side n as a list of strings.
    
    Parameters:
    n (int): The height and base of the triangle.
    
    Returns:
    list: A list of strings where each string represents a row of the triangle.
    """
    # Initialize an empty list to store the rows of the triangle
    triangle = []
    
    # Loop through each row from 1 to n
    for i in range(1, n+1):
        # Create a row with i '*' characters and append it to the list
        triangle.append('*' * i)
    
    # Return the list of rows
    return triangle

# Example Usage
print(generate_triangle(3))  # Output: ['*', '**', '***']
print(generate_triangle(5))  # Output: ['*', '**', '***', '****', '*****']
```

---

### Complexity Analysis

#### Time Complexity
- The loop runs `n` times, and for each row, creating a string of `i` stars takes **O(i)**.
- The total time complexity is the sum of the first `n` natural numbers: **O(1 + 2 + ... + n) = O(n²)**.

#### Space Complexity
- The list `triangle` stores `n` strings, where the `i`th string has `i` characters.
- Therefore, the space complexity is **O(n²)**.

---

### Final Notes
This problem illustrates the basics of pattern generation using loops. Mastering such patterns helps build a strong foundation for solving more complex problems in competitive programming or interviews.
