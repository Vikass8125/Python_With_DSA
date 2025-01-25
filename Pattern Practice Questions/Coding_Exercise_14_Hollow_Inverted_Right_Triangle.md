# Coding Exercise 14: Hollow Inverted Right-Angled Triangle

## Problem Description:

You are given an integer `n`. Your task is to return a hollow inverted right-angled triangle pattern of `*`, where:
- The first row contains `n` stars.
- The inner rows contain a star at the beginning and end, with spaces in between.
- The triangle should be left-aligned.

---

## Input:

A single integer `n`, where `1 <= n <= 100`.

---

## Output:

A list of strings where each string represents a row in the hollow inverted right-angled triangle.

---

## Example:

### Example 1:

**Input:**
```python
4
```

**Output:**
```python
['****', '* *', '**', '*']
```

---

### Example 2:

**Input:**
```python
5
```

**Output:**
```python
['*****', '*  *', '* *', '**', '*']
```

---

## Solution:

### Approach:

1. The pattern consists of `n` rows. We iterate from `n` down to `1`.
2. **First Row:** Contains `n` stars.
3. **Last Row:** Contains a single `*`.
4. **Intermediate Rows:**
   - Contain a `*` at the beginning and end of the row.
   - The spaces between the stars equal `(i - 2)` for the current row `i`.

### Steps:
1. Use a loop that starts from `n` and decrements to `1`.
2. Check the current row:
   - If it’s the first row, add `n` stars.
   - If it’s the last row, add a single `*`.
   - For other rows, add a `*`, followed by spaces, and another `*`.
3. Append each row to a list.
4. Return the final list.

---

### Implementation:

```python
def generate_hollow_inverted_right_angled_triangle(n):
    """
    Function to return a hollow inverted right-angled triangle of '*' of side n as a list of strings.

    Parameters:
    n (int): The height of the triangle.

    Returns:
    list: A list of strings where each string represents a row of the hollow triangle.
    """
    # Initialize an empty list to store the rows of the triangle
    triangle = []

    # Loop through each row from n to 1
    for i in range(n, 0, -1):
        # For the first row, just add 'n' stars
        if i == n:
            triangle.append('*' * n)
        # For the last row, add a single star
        elif i == 1:
            triangle.append('*')
        # For the intermediate rows, add a star, spaces, and another star
        else:
            # Add a star, spaces, and another star
            spaces = ' ' * (i - 2)
            triangle.append('*' + spaces + '*')

    # Return the list of triangle rows
    return triangle
```

---

### Dry Run:

#### Input:
```python
n = 4
```

#### Execution:
1. Initialize `triangle = []`.
2. **Row 4:** `i = 4`
   - Add `****`.
   - `triangle = ['****']`
3. **Row 3:** `i = 3`
   - Add `* *`.
   - `triangle = ['****', '* *']`
4. **Row 2:** `i = 2`
   - Add `**`.
   - `triangle = ['****', '* *', '**']`
5. **Row 1:** `i = 1`
   - Add `*`.
   - `triangle = ['****', '* *', '**', '*']`

#### Output:
```python
['****', '* *', '**', '*']
```

---

### Complexity Analysis:

**Time Complexity:**
- The loop iterates `n` times, and string operations (concatenation and repetition) are performed in each iteration.
- Thus, the time complexity is **O(n)**.

**Space Complexity:**
- The output list contains `n` strings, each of length at most `n`.
- Thus, the space complexity is **O(n)**.

---

### Example Usage:

```python
print(generate_hollow_inverted_right_angled_triangle(4))
# Output: ['****', '* *', '**', '*']

print(generate_hollow_inverted_right_angled_triangle(5))
# Output: ['*****', '*  *', '* *', '**', '*']
