# Coding Exercise 10: Diamond Pattern

## Problem Description

You are given an integer `n`. Your task is to return a diamond pattern of `*` with `n` rows for the upper part (the widest row will have `2n - 1` stars), and the lower part is the mirrored version of the upper part. Each row should be centered with appropriate spaces.

---

### Input
- A single integer `n`, where `1 <= n <= 100`.

### Output
- A list of strings where each string represents a row in the diamond pattern.

---

### Example

#### Input:
```
n = 3
```
#### Output:
```
['  *  ', ' *** ', '*****', ' *** ', '  *  ']
```

#### Input:
```
n = 5
```
#### Output:
```
['    *    ', '   ***   ', '  *****  ', ' ******* ', '*********', ' ******* ', '  *****  ', '   ***   ', '    *    ']
```

---

## Solution

We will solve this problem in two parts:
1. **Brute Force Solution**
2. **Optimal Solution**

Both solutions will generate the upper part of the diamond, followed by the lower part, which is a mirrored version of the upper part.

---

### Brute Force Solution

#### Explanation
1. The upper part of the diamond consists of `n` rows.
   - For the `i`th row (1-based index), the number of stars is `2 * i - 1`.
   - The number of leading spaces is `n - i` to center the stars.
2. The lower part of the diamond consists of `n - 1` rows (excluding the middle row), which is the reverse of the upper part.

We loop through each row, generate the stars and spaces, and append them to the result list.

#### Code
```python
def generate_diamond(n):
    """
    Function to return a diamond pattern of '*' of side n as a list of strings.
    
    Parameters:
    n (int): The number of rows for the upper part of the diamond.
    
    Returns:
    list: A list of strings where each string represents a row of the diamond.
    """
    # Initialize an empty list to store the rows of the diamond
    diamond = []
    
    # Generate the upper part of the diamond (including the middle row)
    for i in range(1, n + 1):
        # Number of stars in the current row is 2 * i - 1
        stars = '*' * (2 * i - 1)
        # Number of leading spaces to center the stars is n - i
        spaces = ' ' * (n - i)
        # Add the centered row to the list
        diamond.append(spaces + stars + spaces)
    
    # Generate the lower part of the diamond (mirrored upper part without the middle row)
    for i in range(n - 1, 0, -1):
        # Number of stars in the current row is 2 * i - 1
        stars = '*' * (2 * i - 1)
        # Number of leading spaces to center the stars is n - i
        spaces = ' ' * (n - i)
        # Add the centered row to the list
        diamond.append(spaces + stars + spaces)
    
    # Return the list of diamond rows
    return diamond
```

#### Example Walkthrough

Let us consider `n = 3`:

1. Upper part:
   - Row 1: Spaces = 2, Stars = 1  => `'  *  '`
   - Row 2: Spaces = 1, Stars = 3  => `' *** '
   - Row 3: Spaces = 0, Stars = 5  => `'*****'
2. Lower part:
   - Row 4: Spaces = 1, Stars = 3  => `' *** '
   - Row 5: Spaces = 2, Stars = 1  => `'  *  '

Final result:
```
['  *  ', ' *** ', '*****', ' *** ', '  *  ']
```

---

### Optimal Solution

#### Explanation
The brute force solution is already efficient with `O(n)` time complexity for generating the diamond, as each row is processed exactly once. Therefore, no significant optimizations are required for this problem.

#### Key Steps
1. Use the same logic to calculate spaces and stars for each row.
2. Append the rows directly to the result list.

#### Code
```python
def generate_diamond(n):
    """
    Optimized function to return a diamond pattern of '*' of side n as a list of strings.
    
    Parameters:
    n (int): The number of rows for the upper part of the diamond.
    
    Returns:
    list: A list of strings where each string represents a row of the diamond.
    """
    diamond = []

    # Generate the upper and lower parts in one loop
    for i in range(1, n + 1):
        stars = '*' * (2 * i - 1)
        spaces = ' ' * (n - i)
        diamond.append(spaces + stars + spaces)
    for i in range(n - 1, 0, -1):
        stars = '*' * (2 * i - 1)
        spaces = ' ' * (n - i)
        diamond.append(spaces + stars + spaces)

    return diamond
```

---

### Complexity Analysis

- **Time Complexity:**
  - Generating each row requires `O(n)` operations for both spaces and stars.
  - Total complexity: `O(n)`.

- **Space Complexity:**
  - The space used is proportional to the number of rows (`2n - 1` strings).
  - Total complexity: `O(n)`.

---

### Example Outputs

#### Example 1:
Input:
```
n = 3
```
Output:
```
['  *  ', ' *** ', '*****', ' *** ', '  *  ']
```

#### Example 2:
Input:
```
n = 5
```
Output:
```
['    *    ', '   ***   ', '  *****  ', ' ******* ', '*********', ' ******* ', '  *****  ', '   ***   ', '    *    ']
