# Coding Exercise 9: Floyd's Triangle

## Problem Description

You are given an integer `n`. Your task is to return the first `n` rows of Floyd’s Triangle, represented as a list of strings. Floyd's Triangle is a triangular array of natural numbers where:
- The first row contains `1`.
- The second row contains `2` and `3`.
- The third row contains `4`, `5`, and `6`.
- And so on.

## Input:

A single integer `n`, where `1 <= n <= 100`.

## Output:

A list of strings where each string represents a row in Floyd's Triangle.

## Example:

### Input:
```
5
```
### Output:
```
['1', '2 3', '4 5 6', '7 8 9 10', '11 12 13 14 15']
```

### Input:
```
3
```
### Output:
```
['1', '2 3', '4 5 6']
```

---

## Solution

```python
def generate_floyds_triangle(n):
    """
    Function to return the first n rows of Floyd's Triangle as a list of strings.

    Parameters:
    n (int): The number of rows in the triangle.

    Returns:
    list: A list of strings where each string represents a row of Floyd's Triangle.
    """
    # Initialize an empty list to store the rows of the triangle
    triangle = []

    # Initialize the first number to be used in the triangle
    current_num = 1

    # Loop through each row from 1 to n
    for i in range(1, n + 1):
        # Create a row by collecting the next i numbers
        row = ' '.join(str(current_num + j) for j in range(i))
        # Append the row to the list
        triangle.append(row)
        # Update the current number for the next row
        current_num += i

    # Return the list of rows
    return triangle
```

---

## Explanation of the Solution

1. **Initialization**:
   - Start with an empty list `triangle` to store the rows.
   - Use a variable `current_num` to keep track of the next number to be added.

2. **Row Construction**:
   - For each row index `i` (from 1 to `n`):
     - Generate `i` consecutive numbers starting from `current_num`.
     - Join these numbers as a string with spaces in between.
     - Append the resulting string to the `triangle` list.

3. **Update**:
   - Increment `current_num` by `i` to start the next row with the correct number.

4. **Return**:
   - Return the `triangle` list, which now contains all `n` rows of Floyd's Triangle.

---

## Dry Run

### Input:
```
3
```

### Execution:
- Start with `triangle = []` and `current_num = 1`.
- Row 1: Collect `1` number starting from `1` → `['1']`. Update `current_num = 2`.
- Row 2: Collect `2` numbers starting from `2` → `['1', '2 3']`. Update `current_num = 4`.
- Row 3: Collect `3` numbers starting from `4` → `['1', '2 3', '4 5 6']`. Update `current_num = 7`.

### Output:
```
['1', '2 3', '4 5 6']
