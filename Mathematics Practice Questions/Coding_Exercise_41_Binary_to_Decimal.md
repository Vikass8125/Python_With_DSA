# Binary to Decimal Conversion

## Problem Description:
You are given a string `binary_str` representing a binary number. Your task is to convert this binary string to its corresponding decimal integer. **Do not use any built-in functions for conversion.**

### Input:
A string `binary_str`, consisting of characters '0' and '1', where the length of the string is between 1 and 30 (inclusive).

### Output:
An integer representing the decimal value of the binary string.

---

### Example:

#### Example 1:
Input: `binary_str = "101"`

Output: `5`

#### Example 2:
Input: `binary_str = "1101"`

Output: `13`

---

### Solution:

#### Approach:
1. Iterate through each character in the binary string from right to left (or in reverse order).
2. Maintain a power counter initialized to 0 to keep track of the current power of 2.
3. For each '1' in the binary string, add the corresponding power of 2 to the result.
4. Increment the power counter for the next digit.
5. Return the calculated decimal value.

#### Implementation:

```python
def binary_to_decimal(binary_str):
    """
    Converts a binary string to its decimal integer representation without using built-in functions.

    Parameters:
    binary_str (str): The binary string to convert.

    Returns:
    int: The decimal representation of the binary string.
    """
    decimal_value = 0
    length = len(binary_str)

    # Iterate over each character in the binary string
    for i in range(length):
        # Get the digit (either '0' or '1')
        digit = binary_str[length - 1 - i]  # Start from the end of the string

        # If the digit is '1', add the corresponding power of 2 to the decimal value
        if digit == '1':
            decimal_value += 2 ** i  # Add 2 raised to the current power

    return decimal_value
```

---

#### Optimized Solution:

The same logic can be implemented using a slightly different approach for better readability:

```python
def binary_to_decimal(binary_str):
    """
    Converts a binary string to its corresponding decimal integer.

    Args:
        binary_str: The binary string to convert.

    Returns:
        The decimal integer equivalent of the binary string.
    """

    decimal = 0
    power = 0

    # Iterate through the binary string in reverse order
    for digit in reversed(binary_str):
        decimal += int(digit) * (2 ** power)
        power += 1

    return decimal
```

---

### Complexity Analysis:

- **Time Complexity:** O(n), where `n` is the length of the binary string. We iterate through the string once.
- **Space Complexity:** O(1), as no additional space is used apart from a few variables.

---

### Test Cases:

```python
# Test Case 1
print(binary_to_decimal("101"))  # Output: 5

# Test Case 2
print(binary_to_decimal("1101"))  # Output: 13

# Test Case 3
print(binary_to_decimal("0"))  # Output: 0

# Test Case 4
print(binary_to_decimal("1"))  # Output: 1

# Test Case 5
print(binary_to_decimal("111111"))  # Output: 63

# Test Case 6
print(binary_to_decimal("100000"))  # Output: 32
```

---

### Hint:
To convert the binary string, use the fact that each digit contributes a power of 2 based on its position from the right (least significant bit). The leftmost bit has the highest power of 2.
