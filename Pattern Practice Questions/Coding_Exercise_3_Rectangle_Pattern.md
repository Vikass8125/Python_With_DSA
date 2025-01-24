# Coding Exercise 3: Rectangle Pattern

## Problem Description
You are given two integers, `n` and `m`. Your task is to return a rectangle pattern of `*`, where:
- `n` represents the number of rows (length).
- `m` represents the number of columns (breadth).

---

## Input
Two integers `n` and `m`, where:
- `1 <= n, m <= 100`

---

## Output
A list of strings where each string represents a row of the rectangle pattern.

---

## Examples

### Example 1:
**Input:**
```
n = 4, m = 5
```
**Output:**
```
['*****', '*****', '*****', '*****']
```

### Example 2:
**Input:**
```
n = 3, m = 2
```
**Output:**
```
['**', '**', '**']
```

---

## Solution Explanation

### Approach
1. **Understand the Pattern:**
   - Each row consists of `m` stars (`*`).
   - There are `n` rows in total.

2. **Steps to Solve:**
   - Initialize an empty list `rectangle` to store the rows.
   - Use a loop that iterates `n` times to generate each row:
     - In each iteration, create a string of `m` stars (`'*' * m`).
     - Append this string to the list `rectangle`.
   - Return the list containing all rows.

---

### Code
```python
def generate_rectangle(n, m):
    """
    Function to return a rectangle pattern of '*' with length n and breadth m as a list of strings.
    
    Parameters:
    n (int): The number of rows in the rectangle.
    m (int): The number of columns in the rectangle.
    
    Returns:
    list: A list of strings where each string represents a row of the rectangle pattern.
    """
    # Initialize an empty list to store the rows of the rectangle
    rectangle = []
    
    # Loop through each row from 1 to n
    for _ in range(n):
        # Create a row with m stars
        row = '*' * m
        # Add the row to the rectangle list
        rectangle.append(row)
    
    # Return the list of rectangle rows
    return rectangle

# Example Usage
print(generate_rectangle(4, 5))  # Output: ['*****', '*****', '*****', '*****']
print(generate_rectangle(3, 2))  # Output: ['**', '**', '**']
```

---

### Complexity Analysis

#### Time Complexity
- The loop runs `n` times, and each row is created in **O(m)** time.
- Thus, the overall time complexity is **O(n * m)**.

#### Space Complexity
- The list `rectangle` stores `n` strings, each of length `m`.
- Therefore, the space complexity is **O(n * m)**.

---

### Final Notes
This exercise demonstrates how to construct rectangular patterns using loops and string operations. By understanding this logic, you can extend it to create more complex patterns like grids or bordered rectangles!
