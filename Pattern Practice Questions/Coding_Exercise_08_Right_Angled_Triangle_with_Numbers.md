# Coding Exercise 8: Right Angled Triangle with Numbers

## Problem Description

You are given an integer `n`. Your task is to return a right-angled triangle pattern where each row contains repeated digits. The first row contains the number `1` repeated once, the second row contains the number `2` repeated twice, and so on until the `n`th row contains the number `n` repeated `n` times.

---

## Input

A single integer `n`, where `1 <= n <= 100`.

---

## Output

A list of strings where each string represents a row in the triangle. The `i`th row contains the digit `i` repeated `i` times.

---

## Examples

### Example 1

**Input:**
```
n = 5
```

**Output:**
```
['1', '22', '333', '4444', '55555']
```

### Example 2

**Input:**
```
n = 3
```

**Output:**
```
['1', '22', '333']
```

---

## Approach and Solution

### Brute Force Approach

We iterate through numbers from `1` to `n` using a loop. For each number `i`, we create a string by repeating the digit `i`, `i` times. The resulting string is added to a list, which is returned at the end.

### Implementation

```python
def generate_number_triangle(n):
    """
    Function to return a right-angled triangle of repeated numbers of side n as a list of strings.
    
    Parameters:
    n (int): The height of the triangle.
    
    Returns:
    list: A list of strings where each string represents a row of the triangle.
    """
    # Initialize an empty list to store the rows of the triangle
    triangle = []
    
    # Loop through each row from 1 to n
    for i in range(1, n + 1):
        # Create a row with the digit i repeated i times
        row = str(i) * i
        # Add the row to the list
        triangle.append(row)
    
    # Return the list of rows
    return triangle
```

---

### Step-by-Step Explanation

1. **Initialization:** Start with an empty list `triangle` to store the rows of the pattern.
2. **Loop through Rows:** Use a loop from `1` to `n`. For each iteration:
   - Convert the current number `i` to a string.
   - Repeat the string `i` times using the `*` operator.
   - Append the resulting string to the `triangle` list.
3. **Return the Result:** Once the loop completes, return the list `triangle`.

---

### Example Walkthrough

#### Example 1: Input `n = 5`

- **Iteration 1:** `i = 1`, `row = '1'`. Append `'1'` to `triangle`.
- **Iteration 2:** `i = 2`, `row = '22'`. Append `'22'` to `triangle`.
- **Iteration 3:** `i = 3`, `row = '333'`. Append `'333'` to `triangle`.
- **Iteration 4:** `i = 4`, `row = '4444'`. Append `'4444'` to `triangle`.
- **Iteration 5:** `i = 5`, `row = '55555'`. Append `'55555'` to `triangle`.

**Output:** `['1', '22', '333', '4444', '55555']`

#### Example 2: Input `n = 3`

- **Iteration 1:** `i = 1`, `row = '1'`. Append `'1'` to `triangle`.
- **Iteration 2:** `i = 2`, `row = '22'`. Append `'22'` to `triangle`.
- **Iteration 3:** `i = 3`, `row = '333'`. Append `'333'` to `triangle`.

**Output:** `['1', '22', '333']`

---

### Complexity Analysis

1. **Time Complexity:**
   - The loop runs `n` times. For each iteration `i`, creating the row takes `O(i)` time.
   - Total time complexity is `O(1 + 2 + 3 + ... + n) = O(n^2)`.

2. **Space Complexity:**
   - The output list contains `n` rows, with the `i`th row having `i` characters.
   - Total space complexity is `O(n^2)`.

---

### Optimal Solution

The above solution is already optimal for this problem. Further optimizations are not necessary as the pattern generation inherently involves quadratic complexity due to the growth of the rows.

---

## Final Thoughts

This problem demonstrates basic string manipulation and list operations in Python. It is an excellent exercise for beginners to practice loops, string operations, and understanding time-space complexity.
