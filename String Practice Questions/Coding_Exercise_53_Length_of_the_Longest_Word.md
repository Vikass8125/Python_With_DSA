# Find the Length of the Longest Word

## Problem Statement

You are given a string `s`. Your task is to find the length of the longest word in the string. A word is defined as a sequence of characters separated by spaces. **Do not use any built-in functions for string manipulation.**

### Parameters:
- `s` (str): The input string containing words separated by spaces. The length of `s` is between 1 and 1000 characters.

### Returns:
- An integer representing the length of the longest word in the string.

---

## Examples

### Example 1:
**Input:**
```python
s = "The quick brown fox jumps over the lazy dog"
```
**Output:**
```python
5
```
**Explanation:**
- The longest word is `jumps`, which has 5 characters.

### Example 2:
**Input:**
```python
s = "Hello World"
```
**Output:**
```python
5
```
**Explanation:**
- Both `Hello` and `World` have 5 characters, so the longest word length is 5.

---

## Solution Approach

We can solve this problem by iterating through the string character by character. We'll keep track of the length of the current word and update the maximum length whenever we encounter a space or reach the end of the string.

### Steps to Solve:
1. **Initialize Variables:**
   - `max_length` to store the length of the longest word (initialized to 0).
   - `current_length` to keep track of the length of the current word (initialized to 0).
2. **Iterate Through the String:**
   - For each character in the string:
     - If it is not a space, increment `current_length`.
     - If it is a space, compare `current_length` with `max_length` and reset `current_length` to 0.
3. **Check the Last Word:**
   - If the string does not end with a space, ensure to compare the final `current_length` with `max_length`.
4. **Return `max_length`:**
   - This represents the length of the longest word in the string.

---

### Brute Force Solution

```python
def longest_word_length(s):
    """
    Function to find the length of the longest word in a string without using built-in functions.
    
    Parameters:
    s (str): The input string.
    
    Returns:
    int: The length of the longest word.
    """
    max_length = 0
    current_length = 0
    
    for i in range(len(s)):
        if s[i] != ' ':  # If the character is not a space
            current_length += 1  # Increment the current word length
        else:
            if current_length > max_length:  # Check if the current word is the longest
                max_length = current_length
            current_length = 0  # Reset current length for the next word

    # Check the last word if the string does not end with a space
    if current_length > max_length:
        max_length = current_length

    return max_length
```

---

### Code Walkthrough

1. **Initialization:**
   - `max_length = 0`: Tracks the maximum word length found so far.
   - `current_length = 0`: Tracks the length of the current word.

2. **Iterating Through the String:**
   - For each character:
     - If it is not a space (`' '`), increment `current_length`.
     - If it is a space, update `max_length` and reset `current_length`.

3. **Final Check:**
   - At the end of the loop, compare `current_length` with `max_length` to ensure the last word is accounted for.

4. **Return the Result:**
   - Return `max_length` as the length of the longest word.

---

### Dry Run

#### Input:
```python
s = "The quick brown fox"
```

#### Execution Steps:
| Step | Character | Current Length | Max Length |
|------|-----------|----------------|------------|
| 1    | `T`       | 1              | 0          |
| 2    | `h`       | 2              | 0          |
| 3    | `e`       | 3              | 0          |
| 4    | ` `       | 0              | 3          |
| 5    | `q`       | 1              | 3          |
| 6    | `u`       | 2              | 3          |
| 7    | `i`       | 3              | 3          |
| 8    | `c`       | 4              | 3          |
| 9    | `k`       | 5              | 3          |
| 10   | ` `       | 0              | 5          |
| 11   | `b`       | 1              | 5          |
| 12   | `r`       | 2              | 5          |
| 13   | `o`       | 3              | 5          |
| 14   | `w`       | 4              | 5          |
| 15   | `n`       | 5              | 5          |
| 16   | ` `       | 0              | 5          |
| 17   | `f`       | 1              | 5          |
| 18   | `o`       | 2              | 5          |
| 19   | `x`       | 3              | 5          |

**Output:**
```python
5
```

---

### Complexity Analysis

1. **Time Complexity:**
   - Iterating through the string takes **O(n)**, where `n` is the length of the string.

2. **Space Complexity:**
   - No additional data structures are used, so the space complexity is **O(1)**.

---

### Optimized Solution

The above solution is already optimal as it iterates through the string once and uses constant space.
