# Coding Exercise 18: Distance Covered by a Vehicle

## Problem Description:
You are given the speed of a vehicle and the time it has traveled. Your task is to compute and return the distance traveled by the vehicle.

### Formula:
To calculate the distance traveled by a vehicle:

\[ {Distance} = {Speed} * {Time} \]

### Input:
- Two floating-point numbers:
  - `speed`: The speed of the vehicle.
  - `time`: The time the vehicle has been traveling.

### Output:
- A floating-point number representing the distance traveled.

---

## Example:

### Example 1:
**Input:**
```python
speed = 60
time = 2
```

**Output:**
```python
120.0
```

**Explanation:**
If a vehicle travels at 60 units of speed for 2 units of time, the distance traveled is:
\[ {Distance} = 60 * 2 = 120 \]

### Example 2:
**Input:**
```python
speed = 50.5
time = 1.5
```

**Output:**
```python
75.75
```

**Explanation:**
If a vehicle travels at 50.5 units of speed for 1.5 units of time, the distance traveled is:
\[ {Distance} = 50.5 * 1.5 = 75.75 \]

---

## Solution:

### Approach 1: Brute Force

In this problem, the formula to calculate the distance is straightforward:

\[ {Distance} = {Speed} * {Time} \]

We will implement this directly in the function.

### Code:
```python
def calculate_distance(speed, time):
    """
    Function to calculate the distance traveled by a vehicle.

    Parameters:
    speed (float): The speed of the vehicle.
    time (float): The time the vehicle has traveled.

    Returns:
    float: The distance traveled by the vehicle.
    """
    # Multiply speed by time to get the distance traveled
    return speed * time
```

### Code Walkthrough:
1. **Function Definition:**
   - The function `calculate_distance` takes two parameters: `speed` and `time`.
2. **Calculation:**
   - Multiply `speed` by `time` to get the distance.
3. **Return:**
   - Return the calculated distance as a floating-point number.

### Dry Run:

#### Example 1:
- **Input:**
  - `speed = 60`
  - `time = 2`
- **Steps:**
  - Multiply `60` by `2`: \( 60 * 2 = 120 \)
- **Output:**
  - `120.0`

#### Example 2:
- **Input:**
  - `speed = 50.5`
  - `time = 1.5`
- **Steps:**
  - Multiply `50.5` by `1.5`: \( 50.5 * 1.5 = 75.75 \)
- **Output:**
  - `75.75`

---

### Approach 2: Optimized Solution
This problem is inherently simple and does not require additional optimization beyond direct multiplication. The provided solution is already optimal in terms of computational complexity.

---

## Complexity Analysis:

- **Time Complexity:**
  - \( O(1) \): The calculation involves a single multiplication operation.

- **Space Complexity:**
  - \( O(1) \): No additional space is used.

---

## Usage:
You can use this function to calculate distances for various scenarios, such as:
- Estimating travel distances for vehicles.
- Calculating distances in simulation programs.

### Example Usage:
```python
# Example 1
print(calculate_distance(60, 2))  # Output: 120.0

# Example 2
print(calculate_distance(50.5, 1.5))  # Output: 75.75
```

---

Happy coding! 😊
