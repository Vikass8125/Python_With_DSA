# Coding Exercise 13: Hollow Right-Angled Triangle

## Problem Description

You are given an integer `n`. Your task is to return a hollow right-angled triangle pattern of `*`, where:
- The first and last rows contain stars (`*`).
- The inner rows contain a star at the beginning and end, with spaces in between.
- The triangle should be right-aligned.

### Input:
A single integer `n`, where `1 <= n <= 100`.

### Output:
A list of strings where each string represents a row in the hollow right-angled triangle.

### Example:

#### Input:
```
4
```

#### Output:
```
['   *', '  **', ' * *', '****']
```

#### Input:
```
5
```

#### Output:
```
['    *', '   **', '  * *', ' *  *', '*****']
```

---

## Solution

We will use a loop to construct each row of the triangle based on the following conditions:
1. The first row contains only one star.
2. The last row contains `n` stars.
3. All intermediate rows have a star at the beginning and end, with spaces in between to form the hollow structure.

### Python Code:
```python
def generate_hollow_right_angled_triangle(n):
    """
    Function to return a hollow right-angled triangle of '*' of side n as a list of strings.

    Parameters:
    n (int): The height of the triangle.

    Returns:
    list: A list of strings where each string represents a row of the hollow triangle.
    """
    # Initialize an empty list to store the rows of the triangle
    triangle = []

    # Loop through each row from 1 to n
    for i in range(1, n + 1):
        # For the first row, just add one star
        if i == 1:
            triangle.append(' ' * (n - i) + '*')
        # For the last row, add 'n' stars
        elif i == n:
            triangle.append('*' * n)
        # For the intermediate rows, add a star, spaces, and another star
        else:
            # Add the row: leading spaces, one star, spaces, and one star
            triangle.append(' ' * (n - i) + '*' + ' ' * (i - 2) + '*')

    # Return the list of triangle rows
    return triangle
```

---

## Explanation with Examples

### Example 1:
#### Input:
```
n = 4
```

#### Execution:
1. For `i = 1`, the row is right-aligned with one star:
   ```
   '   *'
   ```
2. For `i = 2`, the row contains two stars:
   ```
   '  **'
   ```
3. For `i = 3`, the row has a hollow structure with a star at both ends:
   ```
   ' * *'
   ```
4. For `i = 4`, the row is fully filled with stars:
   ```
   '****'
   ```

#### Output:
```
['   *', '  **', ' * *', '****']
```

### Example 2:
#### Input:
```
n = 5
```

#### Execution:
1. For `i = 1`, the row is right-aligned with one star:
   ```
   '    *'
   ```
2. For `i = 2`, the row contains two stars:
   ```
   '   **'
   ```
3. For `i = 3`, the row has a hollow structure:
   ```
   '  * *'
   ```
4. For `i = 4`, the row has another hollow structure:
   ```
   ' *  *'
   ```
5. For `i = 5`, the row is fully filled with stars:
   ```
   '*****'
   ```

#### Output:
```
['    *', '   **', '  * *', ' *  *', '*****']
```

---

## Complexity Analysis

### Time Complexity:
The function iterates `n` times to construct the rows, and each row involves string concatenation, which is proportional to the row's length. Thus, the time complexity is:
- **O(n²)** for constructing the rows.

### Space Complexity:
The function stores all rows in a list, which requires **O(n)** space.

---

## Edge Cases
1. **Minimum Input (`n = 1`):**
   - Input: `1`
   - Output: `['*']`

2. **Larger Input (`n = 6`):**
   - Input: `6`
   - Output:
     ```
     [
         '     *',
         '    **',
         '   * *',
         '  *  *',
         ' *   *',
         '******'
     ]
     ```

---

This completes the implementation and explanation for generating a hollow right-angled triangle.
