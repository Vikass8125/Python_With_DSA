# Pattern Practice Questions

## Coding Exercise 1: Square of side 'N'

### Problem Description
You are given an integer `n`. Your task is to return a square pattern of size `n x n` made up of the character `*`, represented as a list of strings.

### Input Parameters
- `n (int)`: The size of the square (number of rows and columns).

### Output
A list of strings where each string is a row of `n` characters.

---

### Examples

#### Example 1:
**Input:**
```
n = 3
```
**Output:**
```
['***', '***', '***']
```

#### Example 2:
**Input:**
```
n = 5
```
**Output:**
```
['*****', '*****', '*****', '*****', '*****']
```

---

### Solution Explanation

#### Brute Force Approach
1. Initialize an empty list called `square` to store the rows of the pattern.
2. Use a `for` loop to iterate `n` times (once for each row).
3. In each iteration:
   - Create a string of `n` asterisks (`'*' * n`).
   - Append this string to the `square` list.
4. Return the `square` list.

This approach ensures we build each row independently and append it to our result.

---

#### Code for Brute Force Approach
```python
def generate_square(n):
    """
    Function to return a square pattern of '*' of side n as a list of strings.
    
    Parameters:
    n (int): The size of the square.
    
    Returns:
    list: A list of strings where each string represents a row of the square.
    """
    # Initialize an empty list to store the rows of the square
    square = []
    
    # Loop n times to generate each row
    for i in range(n):
        # Create a row of '*' of length n and append it to the list
        square.append('*' * n)
    
    # Return the list of rows
    return square

# Example Usage
print(generate_square(3))  # Output: ['***', '***', '***']
print(generate_square(5))  # Output: ['*****', '*****', '*****', '*****', '*****']
```

---

#### Optimal Solution
In this case, the brute force approach is already optimal. The time complexity is **O(n)** for constructing the rows of the square since we iterate `n` times and create strings of size `n` in each iteration.

#### Why this is Optimal:
- **Space Complexity:** The additional space used is only for the output list, which is required anyway to store the result.
- **Time Complexity:** We only iterate once for each row, ensuring efficiency.

---

### Final Notes
This problem is simple but forms the foundation for more complex pattern generation problems. By understanding the logic here, you can extend your knowledge to create various other patterns like triangles, pyramids, or diamonds.
