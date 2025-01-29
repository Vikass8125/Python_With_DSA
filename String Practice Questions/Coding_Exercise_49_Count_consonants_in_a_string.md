# Count Consonants in a String

## Problem Statement
You are given a string `s`. Your task is to count the number of consonants in the string and return the total count. A consonant is any alphabetic character that is not a vowel (a, e, i, o, u).

### Parameters:
- `s` (str): The input string, where the length of `s` is between **1 and 1000**.

### Returns:
- An integer representing the total count of consonants in the input string.

---

## Examples

### Example 1:
**Input:**
```python
s = "Hello, World!"
```
**Output:**
```python
7
```
**Explanation:**
- The consonants in the string are: `H, l, l, W, r, l, d` (7 in total).

### Example 2:
**Input:**
```python
s = "Python Programming"
```
**Output:**
```python
13
```
**Explanation:**
- The consonants in the string are: `P, y, t, h, n, P, r, g, r, m, m, n, g` (13 in total).

---

## Solution Approach

### Brute Force Approach
1. **Initialize a counter:** Start with `count = 0` to track consonants.
2. **Define vowels:** Store the vowels (`aeiouAEIOU`) in a string.
3. **Iterate through each character:**
   - If the character is an alphabetic letter (`isalpha()`), check if it's **not** a vowel.
   - If it's a consonant, increase the counter.
4. **Return the final count.**

### Brute Force Code Implementation
```python
def count_consonants(s):
    """
    Function to count the number of consonants in the input string.
    
    Parameters:
    s (str): The input string to check for consonants.
    
    Returns:
    int: The count of consonants in the input string.
    """
    vowels = 'aeiouAEIOU'  # Define the set of vowels (both uppercase and lowercase)
    count = 0  # Initialize a counter for consonants
    
    # Loop through each character in the string
    for char in s:
        # Check if the character is a letter
        if char.isalpha() and char not in vowels:
            count += 1  # Increment the count if it is a consonant
    
    return count
```

---

## Code Walkthrough
1. **Define the vowel set:** `vowels = 'aeiouAEIOU'`
2. **Initialize the count variable:** `count = 0`
3. **Loop through each character in the string:**
   - If `char.isalpha()` is `True` and `char not in vowels`, increment `count`.
4. **Return the count.**

---

## Dry Run

### Input:
```python
s = "Hello, World!"
```

### Execution Steps:
| Step | Character | Is Alpha? | Is Vowel? | Count |
|------|----------|-----------|-----------|--------|
| 1    | H        | ✅        | ❌        | 1      |
| 2    | e        | ✅        | ✅        | 1      |
| 3    | l        | ✅        | ❌        | 2      |
| 4    | l        | ✅        | ❌        | 3      |
| 5    | o        | ✅        | ✅        | 3      |
| 6    | ,        | ❌        | -         | 3      |
| 7    | W        | ✅        | ❌        | 4      |
| 8    | o        | ✅        | ✅        | 4      |
| 9    | r        | ✅        | ❌        | 5      |
| 10   | l        | ✅        | ❌        | 6      |
| 11   | d        | ✅        | ❌        | 7      |
| 12   | !        | ❌        | -         | 7      |

**Final Count:** `7`

---

## Optimized Solution
The current solution is already efficient as it processes each character **once**, making it **O(n)** in time complexity. However, we can improve readability by using a `set` for vowels, which allows **O(1)** lookup time.

### Optimized Code Implementation
```python
def count_consonants(s):
    """
    Optimized function to count consonants using a set for vowels.
    """
    vowels = set('aeiouAEIOU')  # Using a set for O(1) lookup time
    return sum(1 for char in s if char.isalpha() and char not in vowels)
```

### Complexity Analysis
- **Time Complexity:** `O(n)`, where `n` is the length of the string.
- **Space Complexity:** `O(1)`, since we use a fixed-size set.

---

## Summary
| Approach        | Time Complexity | Space Complexity | Notes |
|----------------|----------------|------------------|-------|
| Brute Force    | `O(n)`          | `O(1)`           | Iterates through each character checking conditions. |
| Optimized Set  | `O(n)`          | `O(1)`           | Uses a set for `O(1)` vowel lookup. |

This solution effectively counts consonants in a given string while handling non-alphabetic characters efficiently.
