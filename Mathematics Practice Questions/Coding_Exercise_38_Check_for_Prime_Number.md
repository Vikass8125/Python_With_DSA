# Problem: Check if a Number is Prime

## Problem Description:

You are given an integer `n`. Your task is to check whether the number is prime or not. A prime number is a number greater than 1 that has no divisors other than 1 and itself. Return `True` if the number is prime, and `False` otherwise.

### Constraints:
- Input: A single integer `n` where `1 ≤ n ≤ 10^6`.
- Output: Return `True` if `n` is a prime number, otherwise return `False`.

---

### Example:

#### Example 1:
Input: 
```python
n = 5
```
Output: 
```python
True
```
Explanation: 5 is a prime number as it is divisible only by 1 and itself.

#### Example 2:
Input: 
```python
n = 4
```
Output: 
```python
False
```
Explanation: 4 is not a prime number as it is divisible by 2.

---

### Solution:
#### Brute-Force Approach:
The simplest way to check if a number is prime is to check all numbers from `2` to `n-1` and see if any of them divide `n`. If any number divides `n`, it is not a prime number.

#### Code:
```python
def is_prime_brute_force(n):
    """
    Function to check if a number is prime using a brute-force approach.

    Parameters:
    n (int): The number to check.

    Returns:
    bool: True if n is prime, False otherwise.
    """
    # Handle special cases
    if n <= 1:
        return False

    # Check divisibility for numbers from 2 to n-1
    for i in range(2, n):
        if n % i == 0:
            return False

    return True
```

#### Time Complexity:
- **Worst Case**: \(O(n)\), as we are iterating through all numbers from `2` to `n-1`.

---

### Optimized Solution:
Instead of checking all numbers from `2` to `n-1`, we can reduce the range of numbers to check. We only need to check up to the square root of `n`. This is because, if `n` is divisible by any number larger than its square root, then it must also be divisible by a number smaller than its square root.

#### Steps to Optimize:
1. Handle special cases: Any number less than or equal to 1 is not prime, and 2 is the only even prime number.
2. Exclude even numbers greater than 2.
3. Check divisibility for odd numbers up to the square root of `n`.

#### Code:
```python
def is_prime(n):
    """
    Function to check if a number is prime without using built-in functions.

    Parameters:
    n (int): The number to check.

    Returns:
    bool: True if n is prime, False if n is not.
    """
    # Handle special cases
    if n <= 1:
        return False
    if n == 2:  # 2 is a prime number
        return True
    if n % 2 == 0:  # Any even number greater than 2 is not prime
        return False

    # Check divisibility for odd numbers from 3 up to sqrt(n)
    i = 3
    while i * i <= n:
        if n % i == 0:
            return False
        i += 2  # Skip even numbers

    return True
```

#### Time Complexity:
- **Worst Case**: \(O(\sqrt{n})\), as we are only iterating up to the square root of `n`.

---

### Code Walkthrough:
1. **Special Cases**:
   - If `n` is less than or equal to 1, it is not prime.
   - If `n` is 2, it is prime.
   - If `n` is even and greater than 2, it is not prime.

2. **Odd Numbers Check**:
   - Iterate through odd numbers starting from 3 up to the square root of `n`.
   - If any number divides `n` without a remainder, return `False`.
   - If no divisors are found, return `True`.

---

### Examples:
#### Example 1:
Input: 
```python
n = 5
```
Output: 
```python
True
```
Explanation: The number 5 is prime because it is only divisible by 1 and 5.

#### Example 2:
Input: 
```python
n = 4
```
Output: 
```python
False
```
Explanation: The number 4 is not prime because it is divisible by 2.

#### Example 3:
Input: 
```python
n = 29
```
Output: 
```python
True
```
Explanation: The number 29 is prime because it is only divisible by 1 and 29.

---

### Edge Cases:
1. **Smallest Numbers**: Test with inputs like `n = 1` and `n = 2`.
2. **Even Numbers**: Test with even numbers greater than 2, like `n = 10`.
3. **Large Prime Numbers**: Test with a large prime number like `n = 997`.

---

### Test Cases:
```python
# Test Case 1
print(is_prime(1))  # Output: False

# Test Case 2
print(is_prime(2))  # Output: True

# Test Case 3
print(is_prime(10))  # Output: False

# Test Case 4
print(is_prime(29))  # Output: True

# Test Case 5
print(is_prime(997))  # Output: True
```

---

### Conclusion:
By optimizing the solution to check divisibility only up to the square root of the number and skipping even numbers, we significantly reduce the computational complexity from \(O(n)\) to \(O(\sqrt{n})\). This makes the solution efficient and scalable for large inputs.
