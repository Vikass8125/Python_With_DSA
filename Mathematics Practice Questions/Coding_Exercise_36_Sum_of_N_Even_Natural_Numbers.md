# Coding Exercise 36: Sum of N Even Natural Numbers

## Problem Description

You are given an integer `n`. Your task is to calculate and return the sum of the first `n` even natural numbers. The even natural numbers are: 2, 4, 6, 8, ...

---

### Input:
- A single integer `n` where \( 1 \leq n \leq 10^4 \).

### Output:
- Return the sum of the first `n` even natural numbers.

---

## Examples

### Example 1:
**Input:**
```python
n = 3
```
**Output:**
```python
12  # (2 + 4 + 6)
```

### Example 2:
**Input:**
```python
n = 5
```
**Output:**
```python
30  # (2 + 4 + 6 + 8 + 10)
```

---

## Solution Approach

### Steps to Solve:
1. **Generate Even Numbers:**
   - The \( i \)-th even natural number can be expressed as \( 2 \times i \) where \( i \) ranges from 1 to \( n \).
2. **Sum the Numbers:**
   - Add up the first \( n \) even natural numbers.
3. **Return the Sum:**
   - Return the calculated total.

---

### Code Implementation
#### Iterative Approach
```python
def sum_of_even_numbers(n):
    """
    Function to return the sum of the first n even natural numbers.

    Parameters:
    n (int): The number of even numbers to sum.

    Returns:
    int: The sum of the first n even natural numbers.
    """
    total_sum = 0
    current_even_number = 2

    # Loop through the first n even numbers and add them to total_sum
    for i in range(n):
        total_sum += current_even_number
        current_even_number += 2  # Increment by 2 to get the next even number

    return total_sum
```

---

### Code Walkthrough
1. **Initialization:**
   - `total_sum` is initialized to 0 to store the cumulative sum.
   - `current_even_number` is initialized to 2, representing the first even natural number.

2. **Iteration:**
   - Use a loop that iterates \( n \) times.
   - In each iteration:
     - Add the current even number to `total_sum`.
     - Increment the `current_even_number` by 2 to get the next even number.

3. **Return Value:**
   - After the loop ends, return `total_sum`.

---

### Optimized Mathematical Approach
The sum of the first \( n \) even natural numbers can be calculated directly using the formula:
\[ \text{Sum} = n \times (n + 1) \]

#### Code:
```python
def sum_of_even_numbers(n):
    """
    Function to return the sum of the first n even natural numbers using a formula.

    Parameters:
    n (int): The number of even numbers to sum.

    Returns:
    int: The sum of the first n even natural numbers.
    """
    return n * (n + 1)
```

---

## Complexity Analysis

### Iterative Approach:
1. **Time Complexity:**
   - \( O(n) \): The loop runs \( n \) times.

2. **Space Complexity:**
   - \( O(1) \): No additional space is used apart from variables.

### Mathematical Approach:
1. **Time Complexity:**
   - \( O(1) \): The calculation is done in constant time.

2. **Space Complexity:**
   - \( O(1) \): No additional space is used.

---

## Usage
This function can be used in scenarios where:
- You need to calculate the sum of sequences in mathematical problems.
- Summing even numbers in optimization problems.

### Example Usage:
```python
# Example 1
print(sum_of_even_numbers(3))  # Output: 12

# Example 2
print(sum_of_even_numbers(5))  # Output: 30

# Example 3 (Large Input)
print(sum_of_even_numbers(10000))  # Output: 100020000
```

---

Happy coding! 😊
