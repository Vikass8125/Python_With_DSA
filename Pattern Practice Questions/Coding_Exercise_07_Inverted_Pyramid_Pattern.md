# Coding Exercise 8: Right Angled Triangle with Numbers

## Problem Description

You are given an integer `n`. Your task is to return a right-angled triangle pattern where each row contains repeated digits. The first row contains the number `1` repeated once, the second row contains the number `2` repeated twice, and so on until the nth row contains the number `n` repeated `n` times.

---

### Input Parameters
- `n (int)`: The height of the triangle, where `1 <= n <= 100`.

### Output
A list of strings where each string represents a row in the triangle. The `i-th` row contains the digit `i` repeated `i` times.

---

### Example

#### Input:
```
5
```
#### Output:
```
['1', '22', '333', '4444', '55555']
```

#### Input:
```
3
```
#### Output:
```
['1', '22', '333']
```

---

## Solution

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

### Explanation

To solve this problem, we need to create a triangle where:
1. Each row corresponds to a number that is repeated a certain number of times.
2. The `i-th` row has the digit `i` repeated `i` times.

#### Steps:
1. **Initialize the List**: Start with an empty list to store the rows of the triangle.
2. **Iterate Through Rows**: Use a loop from `1` to `n` (inclusive):
   - For each `i`, create a string with the digit `i` repeated `i` times using `str(i) * i`.
   - Append the resulting string to the list.
3. **Return the List**: After the loop, return the list containing all rows of the triangle.

---

### Dry Run

Let’s dry-run the solution with `n = 3`:

1. Initialize `triangle = []`.
2. Loop starts:
   - **i = 1**: `row = '1'`, `triangle = ['1']`
   - **i = 2**: `row = '22'`, `triangle = ['1', '22']`
   - **i = 3**: `row = '333'`, `triangle = ['1', '22', '333']`
3. Return `triangle = ['1', '22', '333']`.

---

### Complexity Analysis

- **Time Complexity**: O(n^2)
  - For each row `i`, generating `str(i) * i` takes O(i), and the loop runs `n` times. The overall complexity is O(1 + 2 + ... + n) = O(n^2).

- **Space Complexity**: O(n^2)
  - The list storing the rows of the triangle has a total of `1 + 2 + ... + n` characters, which is O(n^2).

---

### Optimized Approach
This approach is already optimal for the problem constraints (`1 <= n <= 100`).

---

Let me know if you need further clarifications or enhancements to this solution!
