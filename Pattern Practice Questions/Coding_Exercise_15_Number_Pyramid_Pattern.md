# Coding Exercise 15: Number Pyramid Pattern

## Problem Description

You are given an integer `n`. Your task is to return a pyramid pattern of numbers, where each row contains increasing numbers starting from 1 up to the row number, and the pyramid is centered with leading spaces.

### Input:
A single integer `n`, where `1 <= n <= 100`.

### Output:
A list of strings where each string represents a row in the pyramid pattern.

### Example:

#### Example 1:
**Input:**
```plaintext
4
```
**Output:**
```plaintext
['   1   ', '  1 2  ', ' 1 2 3 ', '1 2 3 4']
```

#### Example 2:
**Input:**
```plaintext
3
```
**Output:**
```plaintext
['  1  ', ' 1 2 ', '1 2 3']
```

---

## Solution

### Approach
To generate a number pyramid pattern, the following steps are used:

1. **Initialization:** Create an empty list `pyramid` to store each row of the pattern.
2. **Iterate through Rows:** Loop through numbers from 1 to `n` to create each row.
   - Add leading spaces to center-align the numbers.
   - Generate a sequence of numbers from 1 to the current row index.
   - Concatenate spaces and numbers to form the row.
3. **Return Result:** Append each row to the `pyramid` list and return it after the loop.

---

### Python Implementation

```python
def generate_number_pyramid(n):
    """
    Function to return a pyramid pattern of numbers of height n as a list of strings.

    Parameters:
    n (int): The height of the pyramid.

    Returns:
    list: A list of strings where each string represents a row of the pyramid pattern.
    """
    # Initialize an empty list to store the rows of the pyramid
    pyramid = []

    # Loop through each row from 1 to n
    for i in range(1, n + 1):
        # Create leading spaces for centering the numbers
        spaces = ' ' * (n - i)
        # Create a string of numbers from 1 to i, joined by spaces
        numbers = ' '.join(str(x) for x in range(1, i + 1))
        # Add the row with spaces and numbers to the pyramid
        pyramid.append(spaces + numbers + spaces)

    # Return the list of pyramid rows
    return pyramid
```

---

### Dry Run

Let’s go through the function step by step with an example:

#### Input:
```plaintext
n = 4
```

#### Execution:
1. **Initialization:**
   - `pyramid = []`

2. **First Iteration (i = 1):**
   - `spaces = ' ' * (4 - 1) = '   '`
   - `numbers = ' '.join(str(x) for x in range(1, 2)) = '1'`
   - Row: `'   1   '`
   - Add to `pyramid`: `['   1   ']`

3. **Second Iteration (i = 2):**
   - `spaces = ' ' * (4 - 2) = '  '`
   - `numbers = ' '.join(str(x) for x in range(1, 3)) = '1 2'`
   - Row: `'  1 2  '`
   - Add to `pyramid`: `['   1   ', '  1 2  ']`

4. **Third Iteration (i = 3):**
   - `spaces = ' ' * (4 - 3) = ' '`
   - `numbers = ' '.join(str(x) for x in range(1, 4)) = '1 2 3'`
   - Row: `' 1 2 3 '`
   - Add to `pyramid`: `['   1   ', '  1 2  ', ' 1 2 3 ']`

5. **Fourth Iteration (i = 4):**
   - `spaces = ' ' * (4 - 4) = ''`
   - `numbers = ' '.join(str(x) for x in range(1, 5)) = '1 2 3 4'`
   - Row: `'1 2 3 4'`
   - Add to `pyramid`: `['   1   ', '  1 2  ', ' 1 2 3 ', '1 2 3 4']`

6. **Return Result:**
   - Final Output: `['   1   ', '  1 2  ', ' 1 2 3 ', '1 2 3 4']`

---

### Complexity Analysis

1. **Time Complexity:**
   - The function iterates through `n` rows.
   - For each row, it generates a sequence of numbers from 1 to the current row index (`i`).
   - **Overall:** O(n^2) due to the nested operations.

2. **Space Complexity:**
   - The space used is proportional to the number of rows and the size of the strings in the list.
   - **Overall:** O(n^2).

---

### Example Outputs

#### Example 1:
**Input:**
```python
n = 4
```
**Output:**
```python
['   1   ', '  1 2  ', ' 1 2 3 ', '1 2 3 4']
```

#### Example 2:
**Input:**
```python
n = 3
```
**Output:**
```python
['  1  ', ' 1 2 ', '1 2 3']
```

#### Example 3:
**Input:**
```python
n = 1
```
**Output:**
```python
['1']
```


