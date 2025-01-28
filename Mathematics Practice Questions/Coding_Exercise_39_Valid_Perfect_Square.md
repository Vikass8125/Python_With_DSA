# Problem Description

You are given a positive integer `num`. Your task is to check whether `num` is a perfect square or not. A perfect square is an integer that is the square of an integer (e.g., 1, 4, 9, 16, ...). Return `True` if `num` is a perfect square, and `False` otherwise.

### Input:
A single positive integer `num` where 1 <= `num` <= 10^9.

### Output:
Return `True` if `num` is a perfect square, otherwise return `False`.

---

### Examples:

**Input:**
```python
num = 16
```
**Output:**
```python
True
```

**Input:**
```python
num = 14
```
**Output:**
```python
False
```

---

### Solution:
```python
def is_perfect_square(num):
    """
    Function to check if a number is a perfect square without using built-in functions.
    
    Parameters:
    num (int): The number to check.
    
    Returns:
    bool: True if num is a perfect square, False if num is not.
    """
    if num < 1:
        return False  # No perfect squares for numbers less than 1
    
    # Initialize a variable to keep track of the current number to check
    i = 1
    
    # Loop until i squared is greater than or equal to num
    while i * i <= num:
        if i * i == num:
            return True  # Found a perfect square
        i += 1  # Increment i to check the next integer
    
    return False  # No perfect square found
```

---

### Explanation:
1. **Problem Understanding:** A perfect square is a number that is the result of squaring an integer. For instance, 4 is a perfect square because it is 2 × 2, and 16 is a perfect square because it is 4 × 4.

2. **Handling Edge Cases:** Numbers less than 1 cannot be perfect squares. For example, `num = 0` or negative numbers are invalid inputs.

3. **Approach:**
   - We start with an integer `i` initialized to 1.
   - We compute the square of `i` in each iteration and check if it equals the input `num`.
   - If we find a match (`i * i == num`), we return `True` because `num` is a perfect square.
   - If the square exceeds `num` without a match, we return `False`.

4. **Efficiency:**
   - The loop runs approximately √`num` times because we only test up to the square root of `num`.
   - This approach avoids unnecessary computations, making it efficient for large values of `num` up to 10^9.

---

### Optimized Solution:

We can optimize this solution using a binary search approach for even better performance on large inputs.

```python
def is_perfect_square(num):
    """
    Optimized function to check if a number is a perfect square using binary search.
    
    Parameters:
    num (int): The number to check.
    
    Returns:
    bool: True if num is a perfect square, False if num is not.
    """
    if num < 1:
        return False  # No perfect squares for numbers less than 1

    # Binary search setup
    low, high = 1, num

    while low <= high:
        mid = (low + high) // 2  # Find the middle element
        squared = mid * mid

        if squared == num:
            return True  # Found the perfect square
        elif squared < num:
            low = mid + 1  # Narrow search to higher values
        else:
            high = mid - 1  # Narrow search to lower values

    return False  # No perfect square found
```

---

### Explanation of Optimized Solution:
1. **Binary Search:**
   - Instead of checking every integer up to √`num`, we divide the range in half during each iteration.
   - Start with the range [1, `num`].
   - Compute the middle value and its square.
   - Depending on whether the square is less than, greater than, or equal to `num`, adjust the range.

2. **Performance:**
   - The binary search algorithm reduces the time complexity to O(log(`num`)), which is highly efficient for large inputs.

---

### Complexity Analysis:
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(√`num`)       | O(1)             |
| Binary Search  | O(log(`num`))   | O(1)             |

---

### Examples:

**Example 1:**
```python
num = 16
print(is_perfect_square(num))  # Output: True
```

**Example 2:**
```python
num = 14
print(is_perfect_square(num))  # Output: False
```

**Example 3 (Optimized):**
```python
num = 25
print(is_perfect_square(num))  # Output: True
```

---
