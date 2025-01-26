# Coding Exercise 16: Celsius to Fahrenheit

## Problem Description:
You are given a temperature in Celsius. Your task is to convert it to Fahrenheit and return the result.

### Formula:
To convert Celsius to Fahrenheit, use the formula:

\[ F = \left(\frac{9}{5} \times C\right) + 32 \]

Where:
- \( F \) is the temperature in Fahrenheit.
- \( C \) is the temperature in Celsius.

### Input:
A floating-point number \( C \) representing the temperature in Celsius.

### Output:
A floating-point number representing the temperature in Fahrenheit.

### Example:
**Input:**
```python
C = 25
```
**Output:**
```python
77.0
```

**Input:**
```python
C = 0
```
**Output:**
```python
32.0
```

---

## Solution:
To solve this problem, we can use the provided formula to convert Celsius to Fahrenheit. This involves multiplying the Celsius value by \( \frac{9}{5} \) and then adding 32.

### Code Implementation:
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

## Explanation of the Code:
1. **Input:** The function takes a single input \( C \), which is the temperature in Celsius.
2. **Formula Application:** The formula \( F = \frac{9}{5} \times C + 32 \) is applied directly.
3. **Output:** The function returns the calculated Fahrenheit value as a floating-point number.

---

## Dry Run:
Let's test the function with an example:

### Example 1:
**Input:**
```python
C = 25
```
**Execution:**
- Apply the formula: \( F = \frac{9}{5} \times 25 + 32 \)
- \( F = 45 + 32 \)
- \( F = 77.0 \)

**Output:**
```python
77.0
```

### Example 2:
**Input:**
```python
C = 0
```
**Execution:**
- Apply the formula: \( F = \frac{9}{5} \times 0 + 32 \)
- \( F = 0 + 32 \)
- \( F = 32.0 \)

**Output:**
```python
32.0
```

---

## Complexity Analysis:
1. **Time Complexity:**
   - The formula involves a constant number of operations (multiplication and addition).
   - **O(1):** The computation is constant-time.

2. **Space Complexity:**
   - The function uses a fixed amount of space for the formula.
   - **O(1):** No additional space is used that grows with input size.

---

## Testing:
You can test the function with different inputs as follows:

```python
# Test cases
print(celsius_to_fahrenheit(25))  # Expected output: 77.0
print(celsius_to_fahrenheit(0))   # Expected output: 32.0
print(celsius_to_fahrenheit(-40)) # Expected output: -40.0
print(celsius_to_fahrenheit(100)) # Expected output: 212.0
```

---

This concludes the solution for converting Celsius to Fahrenheit. Let me know if you have any further questions or need additional explanations!
