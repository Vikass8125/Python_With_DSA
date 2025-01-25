# Coding Exercise 16: Celsius to Fahrenheit

## Problem Description:
You are given a temperature in Celsius. Your task is to convert it to Fahrenheit and return the result.

### Formula:
To convert Celsius to Fahrenheit, use the formula:

\[ F = \left( \frac{9}{5} \times C \right) + 32 \]

Where:
- \( F \) is the temperature in Fahrenheit
- \( C \) is the temperature in Celsius

---

### Input:
- A floating-point number \( C \) representing the temperature in Celsius.

### Output:
- A floating-point number representing the temperature in Fahrenheit.

---

### Examples:

#### Example 1:
**Input:**
```plaintext
C = 25
```
**Output:**
```plaintext
77.0
```

#### Example 2:
**Input:**
```plaintext
C = 0
```
**Output:**
```plaintext
32.0
```

---

## Solution

### Explanation:
The formula to convert Celsius to Fahrenheit is simple and straightforward:

\[ F = \left( \frac{9}{5} \times C \right) + 32 \]

1. Multiply the Celsius value \( C \) by \( \frac{9}{5} \).
2. Add 32 to the result.
3. The final value is the equivalent temperature in Fahrenheit.

This formula comes from the relationship between the two scales, where:
- 0°C = 32°F (freezing point of water)
- 100°C = 212°F (boiling point of water)

By scaling and shifting the values, the formula above is derived.

---

### Code Implementation:
Here is the Python implementation of the solution:

```python
def celsius_to_fahrenheit(C):
    """
    Function to convert temperature from Celsius to Fahrenheit.

    Parameters:
    C (float): The temperature in Celsius.

    Returns:
    float: The temperature in Fahrenheit.
    """
    # Use the conversion formula: F = (9/5 * C) + 32
    return (9 / 5) * C + 32
```

---

### Dry Run:
#### Example 1:
**Input:**
```plaintext
C = 25
```
**Steps:**
1. Apply the formula:
   \[ F = \left( \frac{9}{5} \times 25 \right) + 32 \]
2. Calculate \( \frac{9}{5} \times 25 \):
   \[ 45.0 \]
3. Add 32:
   \[ 45.0 + 32 = 77.0 \]

**Output:**
```plaintext
77.0
```

#### Example 2:
**Input:**
```plaintext
C = 0
```
**Steps:**
1. Apply the formula:
   \[ F = \left( \frac{9}{5} \times 0 \right) + 32 \]
2. Calculate \( \frac{9}{5} \times 0 \):
   \[ 0.0 \]
3. Add 32:
   \[ 0.0 + 32 = 32.0 \]

**Output:**
```plaintext
32.0
```

---

### Complexity Analysis:
1. **Time Complexity:**
   - \( O(1) \): The formula involves a constant number of arithmetic operations regardless of the input.

2. **Space Complexity:**
   - \( O(1) \): No additional data structures are used; only a single floating-point number is returned.

---

### Edge Cases:
1. **Negative Temperatures:**
   - Input: \( C = -40 \)
   - Output: \( -40.0 \) (Both scales intersect at -40.)

2. **Zero Celsius:**
   - Input: \( C = 0 \)
   - Output: \( 32.0 \)

3. **Large Values:**
   - Input: \( C = 1000 \)
   - Output: \( 1832.0 \)

---

### Test Cases:
```python
def test_celsius_to_fahrenheit():
    assert celsius_to_fahrenheit(25) == 77.0
    assert celsius_to_fahrenheit(0) == 32.0
    assert celsius_to_fahrenheit(-40) == -40.0
    assert celsius_to_fahrenheit(100) == 212.0
    assert celsius_to_fahrenheit(37) == 98.6
    print("All test cases pass")

# Run tests
test_celsius_to_fahrenheit()
```

This function is robust, handles edge cases, and ensures accurate conversion for a wide range of inputs.
