# Count Vowels in a String

## Problem Statement

Design a Python function named `count_vowels` to count the number of vowels (both uppercase and lowercase) in a given string and return the total count.

### Parameters:
- `s` (str): The input string with a length between 1 and 1000.

### Returns:
- An integer representing the total count of vowels in the input string.

---

## Examples

### Example 1:
**Input:**
```python
s = "Hello, World!"
```

**Output:**
```python
3
```

**Explanation:**
- The vowels in "Hello, World!" are: 'e', 'o', 'o'.
- The total count of vowels is **3**.

---

### Example 2:
**Input:**
```python
s = "Python Programming"
```

**Output:**
```python
4
```

**Explanation:**
- The vowels in "Python Programming" are: 'o', 'o', 'a', 'i'.
- The total count of vowels is **4**.

---

## Solution Approach

### Brute Force Approach:
1. Define a string containing all vowels (both uppercase and lowercase).
2. Initialize a counter to zero.
3. Loop through each character in the string and check if it is a vowel.
4. If it is a vowel, increment the counter.
5. Return the final count.

### Code Implementation:
```python
def count_vowels(s):
    """
    Function to count the number of vowels in the input string.
    
    Parameters:
    s (str): The input string to check for vowels.
    
    Returns:
    int: The count of vowels in the input string.
    """
    # Define the set of vowels (both lowercase and uppercase)
    vowels = "aeiouAEIOU"
    # Initialize a counter for the vowels
    count = 0
    
    # Loop through each character in the string
    for char in s:
        # Check if the character is a vowel
        if char in vowels:
            count += 1  # Increment the count if it is a vowel
    
    # Return the total count of vowels
    return count
```

---

## Optimal Solution Approach

### Steps to Solve:
1. Convert the input string to lowercase (so we don’t have to check both cases separately).
2. Define a list of vowels.
3. Initialize a counter to zero.
4. Iterate through the characters in the string and count only those that are vowels.
5. Return the final count.

### Optimized Code Implementation:
```python
def count_vowels(s):
    """
    Function to count the number of vowels in the input string.
    
    Parameters:
    s (str): The input string to check for vowels.
    
    Returns:
    int: The count of vowels in the input string.
    """
    s = s.lower()
    count = 0
    # Define the set of vowels
    vowels = ['a', 'e', 'i', 'o', 'u']
    
    for st in s:
        if st in vowels:
            count += 1
    
    return count
```

---

## Code Walkthrough
1. **Convert to Lowercase:**
   - Ensures case insensitivity, so we only check lowercase vowels.

2. **Iterate Through String:**
   - Loop through each character.
   - Check if it belongs to the predefined vowel set.
   - If yes, increment the count.

3. **Return the Count:**
   - After the loop completes, return the total count of vowels.

---

## Complexity Analysis

1. **Time Complexity:**
   - The loop iterates through `n` characters, making it **O(n)**.
   
2. **Space Complexity:**
   - The function uses a few variables, making it **O(1)** (constant space).
