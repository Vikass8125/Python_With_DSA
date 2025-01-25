# Coding Exercise 11: Right-Angled Triangle II

## Problem Description

You are given an integer `n`. Your task is to return a right-angled triangle pattern of `*`, where each row contains stars aligned to the right. The first row has one star, the second row has two stars, and so on, until the nth row has n stars.

### Input:
A single integer `n`, where `1 <= n <= 100`.

### Output:
A list of strings where each string represents a row in the right-angled triangle, right-aligned.

---

### Example

#### Example 1:
**Input:**
```
4
```

**Output:**
```
['   *', '  **', ' ***', '****']
```

#### Example 2:
**Input:**
```
3
```

**Output:**
```
['  *', ' **', '***']
```

---

## Solution

We will solve this problem using two approaches:

### Approach 1: Brute Force

#### Explanation:
1. Start by initializing an empty list `triangle` to store the rows of the triangle.
2. For each row `i` from `1` to `n`:
   - Calculate the number of spaces needed to right-align the row as `n - i`.
   - Calculate the number of stars as `i`.
   - Concatenate the spaces and stars to form the row, then append it to the list.
3. Return the list of rows.

#### Implementation:
```python
def generate_right_angled_triangle(n):
    """
    Function to return a right-angled triangle of '*' of side n as a list of strings.

    Parameters:
    n (int): The height of the triangle.

    Returns:
    list: A list of strings where each string represents a row of the triangle.
    """
    # Initialize an empty list to store the rows of the triangle
    triangle = []

    # Loop through each row from 1 to n
    for i in range(1, n + 1):
        # Number of leading spaces is n - i
        spaces = ' ' * (n - i)
        # Number of stars is i
        stars = '*' * i
        # Add the right-aligned row to the list
        triangle.append(spaces + stars)

    # Return the list of rows
    return triangle
```

#### Complexity Analysis:
- **Time Complexity:** O(n), where `n` is the number of rows. Each row concatenates a fixed number of spaces and stars.
- **Space Complexity:** O(n), for storing the list of `n` rows.

#### Example Walkthrough:
Let us walk through the function for `n = 4`:
1. Row 1: `n - 1 = 3` spaces and `1` star → `'   *'`
2. Row 2: `n - 2 = 2` spaces and `2` stars → `'  **'`
3. Row 3: `n - 3 = 1` space and `3` stars → `' ***'`
4. Row 4: `n - 4 = 0` spaces and `4` stars → `'****'`

**Result:** `['   *', '  **', ' ***', '****']`

---

### Approach 2: Optimal Solution Using List Comprehension

#### Explanation:
We can use Python's list comprehension to generate the rows in a single line by combining spaces and stars dynamically.

#### Implementation:
```python
def generate_right_angled_triangle(n):
    """
    Function to return a right-angled triangle of '*' of side n as a list of strings.

    Parameters:
    n (int): The height of the triangle.

    Returns:
    list: A list of strings where each string represents a row of the triangle.
    """
    return [(' ' * (n - i)) + ('*' * i) for i in range(1, n + 1)]
```

#### Complexity Analysis:
- **Time Complexity:** O(n), as we iterate through `n` rows.
- **Space Complexity:** O(n), for storing the result.

#### Example Walkthrough:
Let us evaluate the list comprehension for `n = 4`:
- Iteration 1 (`i = 1`): `'   *'`
- Iteration 2 (`i = 2`): `'  **'`
- Iteration 3 (`i = 3`): `' ***'`
- Iteration 4 (`i = 4`): `'****'`

**Result:** `['   *', '  **', ' ***', '****']`

---

## Final Thoughts
Both approaches produce the same output. The list comprehension solution is more concise, while the iterative approach is easier to understand for beginners. Choose the one that best suits your coding style or project requirements!
