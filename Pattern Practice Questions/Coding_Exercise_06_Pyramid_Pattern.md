# Coding Exercise 6: Pyramid Pattern

## Problem Description
You are given an integer `n`. Your task is to return a pyramid pattern of `*` where each side has `n` rows, represented as a list of strings. The pyramid is centered, with 1 star in the first row, 3 stars in the second row, and so on, increasing by 2 stars per row until the base row has `2n - 1` stars.

---

## Input Parameters
- `n (int)`: The number of rows in the pyramid, where `1 <= n <= 100`.

---

## Output
A list of strings where each string contains stars (`*`) centered, forming a pyramid shape. Each row has an increasing number of stars, with appropriate spaces for centering.

---

## Examples

### Example 1:
**Input:**
```
n = 3
```
**Output:**
```
['  *  ', ' *** ', '*****']
```

### Example 2:
**Input:**
```
n = 5
```
**Output:**
```
['    *    ', '   ***   ', '  *****  ', ' ******* ', '*********']
```

---

## Solution Explanation

### Approach
1. **Understand the Pattern:**
   - For a pyramid of height `n`:
     - Row 1 has 1 star.
     - Row 2 has 3 stars.
     - Row 3 has 5 stars.
     - ...
     - Row `n` has `2n - 1` stars.
   - Each row is centered, so there are spaces on either side of the stars.

2. **Steps to Solve:**
   - Initialize an empty list `pyramid` to store the rows.
   - Use a loop from `1` to `n` (inclusive):
     - Calculate the number of stars in the current row: `2 * i - 1`.
     - Calculate the number of spaces for centering: `n - i`.
     - Construct the row by combining spaces, stars, and spaces.
     - Append the row to the list `pyramid`.
   - Return the list containing all rows.

---

### Code
```python
def generate_pyramid(n):
    """
    Function to return a pyramid pattern of '*' of side n as a list of strings.
    
    Parameters:
    n (int): The number of rows in the pyramid.
    
    Returns:
    list: A list of strings where each string represents a row of the pyramid.
    """
    # Initialize an empty list to store the rows of the pyramid
    pyramid = []
    
    # Loop through each row from 1 to n
    for i in range(1, n + 1):
        # Number of stars in the current row is 2 * i - 1
        stars = '*' * (2 * i - 1)
        # Number of leading spaces to center the stars is n - i
        spaces = ' ' * (n - i)
        # Add the centered row to the list
        pyramid.append(spaces + stars + spaces)
    
    # Return the list of pyramid rows
    return pyramid

# Example Usage
print(generate_pyramid(3))  # Output: ['  *  ', ' *** ', '*****']
print(generate_pyramid(5))  # Output: ['    *    ', '   ***   ', '  *****  ', ' ******* ', '*********']
```

---

### Complexity Analysis

#### Time Complexity
- The loop runs `n` times, and for each row, creating the string of stars and spaces takes **O(n)**.
- Thus, the overall time complexity is **O(n²)**.

#### Space Complexity
- The list `pyramid` stores `n` strings, each of length `2n - 1`.
- Therefore, the space complexity is **O(n²)**.

---

### Final Notes
This problem is a classic example of pattern generation, involving string manipulation and loops. It helps build fundamental programming skills for solving more complex problems.
