# Coding Exercise 21: Sum of List Elements

## Problem Description:
Write a Python function that calculates the sum of all elements in a given list of integers.

---

### Parameters:
- `numbers` (List of integers): The input list containing integers.

### Returns:
- An integer representing the sum of all elements in the input list.

---

## Example:

### Example 1:
**Input:**
```python
numbers = [1, 2, 3, 4, 5]
```

**Output:**
```python
15
```

**Explanation:**
- Sum of the elements:
  \( 1 + 2 + 3 + 4 + 5 = 15 \)

### Example 2:
**Input:**
```python
numbers = [10, -5, 7, 8, -2]
```

**Output:**
```python
18
```

**Explanation:**
- Sum of the elements:
  \( 10 + (-5) + 7 + 8 + (-2) = 18 \)

---

## Solution:

### Approach 1: Iterative Solution
We will iterate through each element in the list and maintain a running total of the sum.

### Code:
```python
def sum_list(numbers):
    """
    Function to calculate the sum of all elements in a list of integers.

    Parameters:
    numbers (list): A list of integers.

    Returns:
    int: The sum of all elements in the list.
    """
    # Initialize a variable to store the sum
    total = 0

    # Iterate through each number in the list
    for num in numbers:
        # Add the current number to the total
        total += num

    # Return the final sum
    return total
```

### Code Walkthrough:
1. **Initialization:**
   - A variable `total` is initialized to `0` to store the sum.
2. **Iteration:**
   - Each element in the list `numbers` is accessed one by one.
   - The current element is added to `total`.
3. **Return Value:**
   - After the loop ends, the total sum is returned.

---

### Approach 2: Using Built-in `sum()` Function
Python provides a built-in function `sum()` that directly calculates the sum of elements in a list.

### Code:
```python
def sum_list(numbers):
    """
    Function to calculate the sum of all elements in a list of integers using the built-in sum function.

    Parameters:
    numbers (list): A list of integers.

    Returns:
    int: The sum of all elements in the list.
    """
    return sum(numbers)
```

---

## Complexity Analysis:

### Iterative Solution:
- **Time Complexity:**
  - \( O(n) \), where \( n \) is the number of elements in the list. Each element is processed once.
- **Space Complexity:**
  - \( O(1) \), as no additional space is used apart from the `total` variable.

### Using Built-in `sum()`:
- **Time Complexity:**
  - \( O(n) \), as `sum()` internally iterates through the list.
- **Space Complexity:**
  - \( O(1) \), as no additional space is used.

---

## Usage:
This function can be used in various scenarios such as:
- Calculating total marks scored by a student.
- Summing expenses from a list of transactions.

### Example Usage:
```python
# Example 1
print(sum_list([1, 2, 3, 4, 5]))  # Output: 15

# Example 2
print(sum_list([10, -5, 7, 8, -2]))  # Output: 18
```

---

Happy coding! 😊
