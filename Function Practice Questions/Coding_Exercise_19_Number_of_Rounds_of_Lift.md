# Coding Exercise 19: Number of Rounds of Lift

## Problem Description:
You are given `n`, the total number of people, and `capacity`, the maximum number of people the lift can carry at a time. All people want to go from the ground floor to the top floor. Your task is to calculate the number of rounds the lift has to make to transport all the people to the top floor.

---

### Input:
- Two integers:
  - `n`: The total number of people.
  - `capacity`: The maximum number of people the lift can carry in one round.

### Output:
- An integer representing the number of rounds the lift needs to cover to transport all people to the top floor.

---

## Example:

### Example 1:
**Input:**
```python
n = 10
capacity = 3
```

**Output:**
```python
4
```

**Explanation:**
- The lift can carry 3 people at a time.
- Total people: 10.
- Full rounds: \( {10 // 3} = 3 \).
- Remaining people: \( {10 \% 3} = 1 \).
- Total rounds required: \( 3 + 1 = 4 \).

### Example 2:
**Input:**
```python
n = 7
capacity = 4
```

**Output:**
```python
2
```

**Explanation:**
- The lift can carry 4 people at a time.
- Total people: 7.
- Full rounds: \( {7 // 4} = 1 \).
- Remaining people: \( {7 \% 4} = 3 \).
- Total rounds required: \( 1 + 1 = 2 \).

---

## Solution:

### Approach 1: Brute Force
The problem can be solved directly by dividing the total number of people (`n`) by the lift's capacity (`capacity`) and checking if there are any remaining people. If there are, we add one additional round.

### Code:
```python
def calculate_lift_rounds(n, capacity):
    """
    Function to calculate the number of rounds the lift needs to cover.

    Parameters:
    n (int): Total number of people.
    capacity (int): Maximum number of people the lift can carry in one round.

    Returns:
    int: The number of rounds required to transport all people to the top floor.
    """
    # Divide total people by the capacity to get full rounds
    full_rounds = n // capacity

    # If there are any remaining people, add one more round
    if n % capacity != 0:
        return full_rounds + 1
    else:
        return full_rounds
```

### Code Walkthrough:
1. **Function Definition:**
   - The function `calculate_lift_rounds` takes two parameters: `n` (number of people) and `capacity` (maximum lift capacity).
2. **Full Rounds Calculation:**
   - Use integer division (`//`) to calculate the number of full rounds the lift can make.
3. **Check for Remaining People:**
   - Use the modulo operator (`%`) to check if there are people left after the full rounds.
   - If there are, add one additional round.
4. **Return Value:**
   - Return the total number of rounds as an integer.

---

### Dry Run:

#### Example 1:
- **Input:**
  - `n = 10`
  - `capacity = 3`
- **Steps:**
  1. Calculate full rounds: \( {10 // 3} = 3 \).
  2. Calculate remaining people: \( {10 \% 3} = 1 \).
  3. Total rounds: \( 3 + 1 = 4 \).
- **Output:**
  - `4`

#### Example 2:
- **Input:**
  - `n = 7`
  - `capacity = 4`
- **Steps:**
  1. Calculate full rounds: \( {7 // 4} = 1 \).
  2. Calculate remaining people: \( {7 \% 4} = 3 \).
  3. Total rounds: \( 1 + 1 = 2 \).
- **Output:**
  - `2`

---

### Approach 2: Optimized Solution
This problem is simple and does not require additional optimization beyond the direct calculation provided in the brute force method.

---

## Complexity Analysis:

- **Time Complexity:**
  - \( O(1) \): The calculation involves basic arithmetic operations.

- **Space Complexity:**
  - \( O(1) \): No additional space is used.

---

## Usage:
This function can be used in scenarios where:
- You need to calculate logistics for transporting people.
- Simulating real-life lift operations in buildings or simulations.

### Example Usage:
```python
# Example 1
print(calculate_lift_rounds(10, 3))  # Output: 4

# Example 2
print(calculate_lift_rounds(7, 4))  # Output: 2
```

---

Happy coding! 😊
