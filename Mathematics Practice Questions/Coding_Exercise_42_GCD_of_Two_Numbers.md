# GCD of Two Numbers

## Problem Statement

You are given two integers `n` and `m`. Your task is to find the **Greatest Common Divisor (GCD)** of these two numbers. The **GCD** is the largest positive integer that divides both numbers without leaving a remainder.

**Constraints:**
- `1 <= n, m <= 10^9`
- Do **not** use any built-in functions and **do not** use recursion.

---

## Examples

### Example 1:
**Input:**
```python
n = 48
m = 18
```
**Output:**
```python
6
```
**Explanation:**
- The factors of `48` are `{1, 2, 3, 4, 6, 8, 12, 16, 24, 48}`.
- The factors of `18` are `{1, 2, 3, 6, 9, 18}`.
- The common factors are `{1, 2, 3, 6}` and the largest one is `6`.

### Example 2:
**Input:**
```python
n = 56
m = 98
```
**Output:**
```python
14
```
**Explanation:**
- The factors of `56` are `{1, 2, 4, 7, 8, 14, 28, 56}`.
- The factors of `98` are `{1, 2, 7, 14, 49, 98}`.
- The common factors are `{1, 2, 7, 14}` and the largest one is `14`.

---

## Solution Approach

### Brute Force Approach:
#### Steps:
1. Find the minimum of `n` and `m`.
2. Iterate from `1` to this minimum value.
3. Check if `i` is a divisor of both numbers.
4. Keep track of the largest common divisor found.
5. Return the largest common divisor.

### Code Implementation:
```python
def find_gcd(n1, n2):
    # Initialize gcd to 1
    gcd = 1

    # Iterate from 1 up to the minimum of n1 and n2
    for i in range(1, min(n1, n2) + 1):
        # Check if i is a common factor of both n1 and n2
        if n1 % i == 0 and n2 % i == 0:
            # Update gcd to the current common factor i
            gcd = i
    
    # Return the greatest common divisor
    return gcd
```

### Code Walkthrough:
1. We start by initializing `gcd = 1`.
2. We iterate from `1` to `min(n1, n2)`.
3. For each `i`, check if both numbers are divisible by `i`.
4. If true, update `gcd` to `i`.
5. At the end, `gcd` will hold the largest common divisor.

### Complexity Analysis:
- **Time Complexity:** `O(min(n, m))` (as we check every number up to the smaller value).
- **Space Complexity:** `O(1)` (only a few integer variables are used).

---

## Optimal Approach: Euclidean Algorithm
#### Steps:
1. Ensure `n` and `m` are positive.
2. Use the **Euclidean algorithm**, which works as follows:
   - Swap `n` and `m`, assigning `m` to `n` and `n % m` to `m`.
   - Repeat until `m` becomes `0`.
   - The final `n` is the GCD.

### Code Implementation:
```python
def gcd(n, m):
    """
    Function to find the GCD of two integers without using built-in functions and recursion.
    """
    # Ensure n and m are positive
    n = abs(n)
    m = abs(m)
 
    # Use the Euclidean algorithm iteratively
    while m != 0:
        n, m = m, n % m  # Assign m to n and remainder of n divided by m to m
 
    return n  # When m becomes 0, n is the GCD
```

### Code Walkthrough:
1. We take the absolute values of `n` and `m`.
2. We iterate while `m != 0`.
3. In each step, we set `n = m` and `m = n % m`.
4. When `m` becomes `0`, `n` contains the GCD.

### Complexity Analysis:
- **Time Complexity:** `O(log(min(n, m)))` (since the Euclidean algorithm runs in logarithmic time).
- **Space Complexity:** `O(1)` (only a few integer variables are used).

---

### Comparison of Approaches
| Approach          | Time Complexity  | Space Complexity | Performance |
|------------------|----------------|----------------|-------------|
| Brute Force     | `O(min(n, m))`  | `O(1)`         | Slow        |
| Euclidean Algo  | `O(log(min(n, m)))` | `O(1)`         | Fast ✅    |

---

### Summary:
- The **Brute Force** approach checks all numbers up to `min(n, m)`, which is slow.
- The **Euclidean Algorithm** optimally reduces the numbers using modulo operations, making it efficient.
- Always prefer the **Euclidean Algorithm** for computing GCD efficiently! 🚀
