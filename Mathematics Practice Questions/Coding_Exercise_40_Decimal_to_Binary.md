# Problem Description

You are given an integer `n`. Your task is to return its binary representation as a string. Do not use any built-in functions for conversion.

## Input:
A single integer `n`, where \(-10^9 \leq n \leq 10^9\).

## Output:
A string representing the binary representation of `n`.

---

## Example:

### Example 1:
**Input:**
```plaintext
n = 5
```
**Output:**
```plaintext
"101"
```

### Example 2:
**Input:**
```plaintext
n = -5
```
**Output:**
```plaintext
"-101"
```

---

## Solution:
We will implement two functions to convert an integer to its binary representation manually. The functions will:
1. Check for special cases (e.g., when `n` is zero).
2. Handle negative numbers by converting them to positive values and appending a negative sign.
3. Build the binary string by repeatedly dividing the number by 2 and recording the remainders.

### Solution 1: Step-by-Step Conversion
```python
def int_to_binary(n):
    """
    Function to convert an integer to its binary representation.
    
    Parameters:
    n (int): The integer to convert.
    
    Returns:
    str: The binary representation of the integer.
    """
    if n == 0:
        return "0"  # Special case for zero

    result = ""
    is_negative = False

    # Handle negative numbers
    if n < 0:
        is_negative = True
        n = -n

    # Convert to binary
    while n > 0:
        result = str(n % 2) + result  # Prepend the remainder
        n //= 2  # Floor divide by 2

    # Add the negative sign for negative numbers
    if is_negative:
        result = "-" + result

    return result
```

---

### Solution 2: Optimized Approach
This function follows a similar logic but uses a slightly different implementation to achieve the same goal.

```python
def int_to_binary(n):
    """
    Function to convert an integer to its binary representation without using built-in functions.
    
    Parameters:
    n (int): The integer to convert.
    
    Returns:
    str: The binary representation of the integer.
    """
    if n == 0:
        return "0"  # Special case for zero
 
    # Store the binary representation
    binary_representation = ""
    
    # Handle negative numbers
    is_negative = n < 0
    if is_negative:
        n = -n  # Work with the absolute value
 
    # Convert to binary
    while n > 0:
        remainder = n % 2
        binary_representation = str(remainder) + binary_representation  # Prepend the remainder
        n = n // 2  # Update n to be n divided by 2 (floor division)
 
    # Add the negative sign for negative numbers
    if is_negative:
        binary_representation = "-" + binary_representation
 
    return binary_representation
```

---

## Explanation of the Algorithm
1. **Handle Zero:**
   - If `n == 0`, immediately return "0" as the binary representation of zero is itself.

2. **Check for Negativity:**
   - If `n` is negative, set a flag `is_negative` and work with the absolute value of `n` to simplify the conversion process. Later, prepend a negative sign to the result.

3. **Construct the Binary Representation:**
   - Use a loop to divide `n` by 2 repeatedly until it becomes zero.
   - For each division, record the remainder (`n % 2`) and prepend it to the result string.

4. **Return Result:**
   - If the number was negative, add a negative sign before returning the result.
   - Otherwise, return the constructed binary string as is.

---

## Dry Run:
### Example 1:
**Input:**
```plaintext
n = 5
```

| Step | Value of `n` | Remainder | Binary String |
|------|--------------|-----------|---------------|
| 1    | 5            | 1         | "1"           |
| 2    | 2            | 0         | "01"          |
| 3    | 1            | 1         | "101"         |
| 4    | 0            | -         | "101"         |

**Output:**
```plaintext
"101"
```

### Example 2:
**Input:**
```plaintext
n = -5
```

| Step | Value of `n` | Remainder | Binary String |
|------|--------------|-----------|---------------|
| 1    | 5            | 1         | "1"           |
| 2    | 2            | 0         | "01"          |
| 3    | 1            | 1         | "101"         |
| 4    | 0            | -         | "-101"        |

**Output:**
```plaintext
"-101"
```

---

## Complexity Analysis:
1. **Time Complexity:**
   - The algorithm performs \(O(\log_2{n})\) iterations since the number of divisions by 2 corresponds to the number of bits in `n`.

2. **Space Complexity:**
   - The space complexity is \(O(\log_2{n})\) due to the storage of the binary representation string.

---

### Test Cases:
```python
print(int_to_binary(5))    # Output: "101"
print(int_to_binary(-5))   # Output: "-101"
print(int_to_binary(0))    # Output: "0"
print(int_to_binary(1))    # Output: "1"
print(int_to_binary(-1))   # Output: "-1"
print(int_to_binary(1024)) # Output: "10000000000"
