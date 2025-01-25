# Coding Exercise 12: Sandglass Pattern

## Problem Description:

You are given an integer `n`. Your task is to return a sandglass pattern of `*`, where:
- The first row contains `2n - 1` stars, and each subsequent row decreases the number of stars by 2 until the last row contains a single star.
- After reaching the smallest width, the pattern continues with the same number of stars increasing back to `2n - 1`.
- The stars in each row should be centered.

---

### Input:
- A single integer `n`, where `1 <= n <= 100`.

### Output:
- A list of strings where each string represents a row in the sandglass pattern.

---

### Example:

#### Example 1:
**Input:**
```python
n = 3
```

**Output:**
```python
['*****', ' *** ', '  *  ', ' *** ', '*****']
```

#### Example 2:
**Input:**
```python
n = 4
```

**Output:**
```python
['*******', ' ***** ', '  ***  ', '   *   ', '  ***  ', ' ***** ', '*******']
```

---

## Solution:

We will approach the problem step by step:

### Brute Force Approach:

1. **Understanding the Pattern:**
   - The sandglass has two parts:
     1. The upper half: Starts with `2n - 1` stars and reduces by 2 stars per row.
     2. The lower half: Starts with 1 star and increases by 2 stars per row until it matches the width of the first row.
   - Stars in each row are centered with spaces.

2. **Algorithm:**
   - For the upper half:
     1. Loop from `0` to `n - 1` (inclusive).
     2. For each row, calculate the number of stars and leading spaces.
   - For the lower half:
     1. Loop from `n - 2` to `0` (inclusive, reversed).
     2. Calculate stars and spaces in the same way as the upper half.

3. **Implementation:**
```python
def generate_sandglass(n):
    """
    Function to return a sandglass pattern of '*' of side n as a list of strings.

    Parameters:
    n (int): The height of the sandglass.

    Returns:
    list: A list of strings where each string represents a row of the sandglass pattern.
    """
    # Initialize an empty list to store the rows of the sandglass
    sandglass = []

    # Create the upper half of the sandglass (including the narrowest row)
    for i in range(n):
        # Calculate the number of stars: 2 * (n - i) - 1
        stars = '*' * (2 * (n - i) - 1)
        # Calculate the number of leading spaces to center the stars
        spaces = ' ' * i
        # Add the centered row to the list
        sandglass.append(spaces + stars + spaces)

    # Create the lower half of the sandglass (excluding the narrowest row)
    for i in range(n - 1):
        # Calculate the number of stars: 2 * (i + 1) + 1
        stars = '*' * (2 * (i + 1) + 1)
        # Calculate the number of leading spaces for the lower half
        spaces = ' ' * (n - i - 2)
        # Add the centered row to the list, ensuring proper spacing
        sandglass.append(spaces + stars + spaces)

    # Return the list of sandglass rows
    return sandglass
```

### Dry Run:

#### Example Input:
```python
n = 3
```

**Step-by-Step Execution:**

- **Upper Half:**
  - Row 1: Spaces = `0`, Stars = `*****` → `'*****'`
  - Row 2: Spaces = `1`, Stars = ` *** ` → `' *** '
  - Row 3: Spaces = `2`, Stars = `  *  ` → `'  *  '

- **Lower Half:**
  - Row 4: Spaces = `1`, Stars = ` *** ` → `' *** '
  - Row 5: Spaces = `0`, Stars = `*****` → `'*****'

**Final Output:**
```python
['*****', ' *** ', '  *  ', ' *** ', '*****']
```

---

### Optimal Solution:

The above approach is already optimal, as we use simple loops to construct the pattern, with a time complexity of **O(n)** (one pass for the upper and lower halves).

---

## Example Usage:
```python
# Input
n = 4

# Function Call
result = generate_sandglass(n)

# Output
print("\n".join(result))
```

**Output:**
```
*******
 ***** 
  ***  
   *   
  ***  
 ***** 
*******
```

---

## Complexity Analysis:

- **Time Complexity:**
  - Constructing the upper half: O(n).
  - Constructing the lower half: O(n).
  - Total: **O(n)**.

- **Space Complexity:**
  - Storing the pattern in a list: **O(n)**.

---

Feel free to experiment with different values of `n` to see how the sandglass pattern adapts!
