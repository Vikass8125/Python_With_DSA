# Coding Exercise 20: Line Equation

## Problem Description:
You are given the slope `m` and the y-intercept `b` of a line, along with a value `x`. Your task is to calculate and return the value of `y` using the equation of a line in slope-intercept form:

\[ y = mx + b \]

---

### Input:
- Three floating-point numbers:
  - `slope`: The slope of the line (`m`).
  - `intercept`: The y-intercept of the line (`b`).
  - `x`: The value of `x` for which `y` needs to be calculated.

### Output:
- A floating-point number representing the value of `y` corresponding to the given `x`.

---

## Example:

### Example 1:
**Input:**
```python
slope = 2
intercept = 3
x = 4
```

**Output:**
```python
11.0
```

**Explanation:**
The equation of the line is:
\[ y = 2x + 3 \]
Substitute \( x = 4 \):
\[ y = (2 * 4) + 3 = 8 + 3 = 11 \]

### Example 2:
**Input:**
```python
slope = 1.5
intercept = -2
x = 2
```

**Output:**
```python
1.0
```

**Explanation:**
The equation of the line is:
\[ y = 1.5x - 2 \]
Substitute \( x = 2 \):
\[ y = (1.5 * 2) - 2 = 3 - 2 = 1 \]

---

## Solution:

### Approach 1: Direct Calculation
The formula for the slope-intercept form of a line is straightforward:

\[ y = mx + b \]

We will implement this formula in a function to calculate `y` for given values of `slope`, `intercept`, and `x`.

### Code:
```python
def calculate_y(slope, intercept, x):
    """
    Function to calculate the value of y using the slope-intercept form of a line.

    Parameters:
    slope (float): The slope of the line.
    intercept (float): The y-intercept of the line.
    x (float): The value of x for which y needs to be calculated.

    Returns:
    float: The calculated value of y.
    """
    # Use the slope-intercept formula to calculate y
    y = (slope * x) + intercept
    return y
```

### Code Walkthrough:
1. **Function Definition:**
   - The function `calculate_y` takes three parameters: `slope`, `intercept`, and `x`.
2. **Calculation:**
   - Compute \( y \) using the formula \( y = mx + b \), where:
     - \( m \) is the slope.
     - \( b \) is the y-intercept.
     - \( x \) is the input value.
3. **Return Value:**
   - Return the calculated value of \( y \) as a floating-point number.

---

### Dry Run:

#### Example 1:
- **Input:**
  - `slope = 2`
  - `intercept = 3`
  - `x = 4`
- **Steps:**
  1. Calculate \( y \):
     \[ y = (2 * 4) + 3 = 8 + 3 = 11 \]
- **Output:**
  - `11.0`

#### Example 2:
- **Input:**
  - `slope = 1.5`
  - `intercept = -2`
  - `x = 2`
- **Steps:**
  1. Calculate \( y \):
     \[ y = (1.5 * 2) - 2 = 3 - 2 = 1 \]
- **Output:**
  - `1.0`

---

### Approach 2: Optimized Solution
This problem is inherently simple, and the direct calculation is already optimal. No further optimization is required.

---

## Complexity Analysis:

- **Time Complexity:**
  - \( O(1) \): The calculation involves a single multiplication and addition.

- **Space Complexity:**
  - \( O(1) \): No additional space is used.

---

## Usage:
This function can be used in scenarios such as:
- Predicting values in linear regression models.
- Calculating line equations in geometry problems.

### Example Usage:
```python
# Example 1
print(calculate_y(2, 3, 4))  # Output: 11.0

# Example 2
print(calculate_y(1.5, -2, 2))  # Output: 1.0
```

---

Happy coding! 😊
