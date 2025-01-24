# Coding Exercise 5: Inverted Right-Angled Triangle

## Problem Description
You are given an integer `n`. Your task is to return an inverted right-angled triangle pattern of `*` where each side has `n` characters, represented as a list of strings. The first row should have `n` stars, the second row `n-1` stars, and so on, until the last row has 1 star.

---

## Input Parameters
- `n (int)`: The height and base of the inverted right-angled triangle.

---

## Output
A list of strings where each string is a row of `*` characters that decreases in length from `n` to 1.

---

## Examples

### Example 1:
**Input:**
```
n = 3
```
**Output:**
```
['***', '**', '*']
```

### Example 2:
**Input:**
```
n = 5
```
**Output:**
```
['*****', '****', '***', '**', '*']
```

---

## Solution Explanation

### Approach
1. **Understand the Pattern:**
   - The first row contains `n` stars.
   - The second row contains `n-1` stars.
   - This continues until the last row, which contains 1 star.

2. **Steps to Solve:**
   - Initialize an empty list `triangle` to store the rows.
   - Use a loop that iterates from `n` down to 1 (inclusive):
     - In each iteration, create a string of `i` stars (`'*' * i`) where `i` is the current row number.
     - Append this string to the list `triangle`.
   - Return the list containing all rows.

---

### Code
```python
def generate_inverted_triangle(n):
    """
    Function to return an inverted right-angled triangle of '*' of side n as a list of strings.
    
    Parameters:
    n (int): The height and base of the triangle.
    
    Returns:
    list: A list of strings where each string represents a row of the triangle.
    """
    # Initialize an empty list to store the rows of the triangle
    triangle = []
    
    # Loop from n down to 1 (inclusive) to create each row
    for i in range(n, 0, -1):
        # Create a row with i '*' characters and append it to the list
        triangle.append('*' * i)
    
    # Return the list of rows
    return triangle

# Example Usage
print(generate_inverted_triangle(3))  # Output: ['***', '**', '*']
print(generate_inverted_triangle(5))  # Output: ['*****', '****', '***', '**', '*']
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
This problem helps build a solid understanding of pattern generation using loops and basic string operations. Mastering such patterns is essential for developing logical thinking in programming.
