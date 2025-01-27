# Coding Exercise 37: Check for Even Number

## Problem Description

You are given an integer `n`. Your task is to check whether the number is even or not. Return `True` if the number is even, and `False` otherwise.

---

### Input:
- A single integer `n` where \( -10^9 \leq n \leq 10^9 \).

### Output:
- Return `True` if `n` is an even number, otherwise return `False`.

---

## Examples

### Example 1:
**Input:**
```python
n = 4
```
**Output:**
```python
True
```
**Explanation:**
- The number 4 is even because it is divisible by 2 without a remainder.

### Example 2:
**Input:**
```python
n = 7
```
**Output:**
```python
False
```
**Explanation:**
- The number 7 is odd because dividing it by 2 leaves a remainder.

---

## Solution Approach

### Steps to Solve:
1. **Check Divisibility by 2:**
   - A number is even if dividing it by 2 leaves no remainder.
   - Use the modulo operator `%` to check if `n % 2 == 0`.
2. **Return Result:**
   - If the condition `n % 2 == 0` is `True`, return `True` (even number).
   - Otherwise, return `False` (odd number).

---

### Code Implementation
```python
def is_even(n):
    """
    Function to check if a number is even.

    Parameters:
    n (int): The number to check.

    Returns:
    bool: True if n is even, False if n is odd.
    """
    # A number is even if dividing it by 2 leaves no remainder
    if n % 2 == 0:
        return True
    else:
        return False
```

---

### Optimized Code
The `if-else` condition can be simplified into a single line using a return statement.

#### Code:
```python
def is_even(n):
    """
    Optimized function to check if a number is even.

    Parameters:
    n (int): The number to check.

    Returns:
    bool: True if n is even, False if n is odd.
    """
    return n % 2 == 0
```

---

### Code Walkthrough
1. **Input Check:**
   - Given `n = 4`, check if `4 % 2 == 0`.
2. **Modulo Operation:**
   - `4 % 2` results in `0` because 4 is divisible by 2.
3. **Return Value:**
   - Since `0 == 0` is `True`, the function returns `True`.

---

### Complexity Analysis

1. **Time Complexity:**
   - \( O(1) \): The modulo operation is constant time.

2. **Space Complexity:**
   - \( O(1) \): No additional space is used.

---

## Usage
This function can be used in scenarios such as:
- Filtering even numbers from a list.
- Validating inputs in number-based operations.

### Example Usage:
```python
# Example 1
print(is_even(4))  # Output: True

# Example 2
print(is_even(7))  # Output: False

# Example 3
print(is_even(0))  # Output: True

# Example 4 (Negative Number)
print(is_even(-6))  # Output: True
```

---

Happy coding! 😊
