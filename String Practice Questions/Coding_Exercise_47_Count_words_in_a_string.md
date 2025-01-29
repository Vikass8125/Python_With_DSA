# Count Words in a String

## Problem Statement

Design a Python function named `count_words` to count the number of words in a given string. A word is defined as a sequence of characters separated by spaces.

### Parameters:
- `s` (str): The input string where you need to count the number of words.

### Returns:
- An integer representing the total count of words in the input string.

---

## Examples

### Example 1:
**Input:**
```python
s = "Hello, World!"
```
**Output:**
```python
2
```
**Explanation:**
- The string contains two words: `"Hello,"` and `"World!"`.

### Example 2:
**Input:**
```python
s = "Python programming is fun."
```
**Output:**
```python
4
```
**Explanation:**
- The string contains four words: `"Python"`, `"programming"`, `"is"`, and `"fun."`.

---

## Solution Approach

### Steps to Solve:
1. **Iterative Method (No Built-in Functions):**
   - Initialize a counter `count` to 0.
   - Use a flag `in_word` to track if we are inside a word.
   - Iterate through each character in the string:
     - If the character is not a space and `in_word` is False, increment `count` and set `in_word` to True.
     - If the character is a space, set `in_word` to False.
   - Return the `count`.

2. **Using Built-in Functions:**
   - Use the `split()` method to break the string into words based on spaces.
   - Return the length of the resulting list.

---

### Code Implementation (Iterative Method)
```python
def count_words(s):
    """
    Function to count the number of words in the input string without using built-in functions.

    Parameters:
    s (str): The input string to check for words.

    Returns:
    int: The count of words in the input string.
    """
    count = 0  # Initialize a counter for the number of words
    in_word = False  # Flag to track if we are inside a word

    # Loop through each character in the string
    for char in s:
        # Check if the character is not a space
        if char != ' ':
            if not in_word:  # If we were not in a word before
                in_word = True  # Set the flag to indicate we are now in a word
                count += 1  # Increment the word count
        else:
            in_word = False  # If we encounter a space, we are not in a word anymore

    return count  # Return the total count of words
```

### Code Implementation (Using Built-in Functions)
```python
def count_words(s):
    """
    Function to count the number of words in the input string.

    Parameters:
    s (str): The input string to check for words.

    Returns:
    int: The count of words in the input string.
    """
    # Split the string into words based on spaces
    words = s.split()

    # Return the length of the resulting list of words
    return len(words)
```

---

### Code Walkthrough (Iterative Method)
1. **Input String:**
   - Example: `"Hello, World!"`
2. **Initialization:**
   - `count = 0`
   - `in_word = False`
3. **Iteration:**
   - First character: `"H"` (not a space, `in_word` is False):
     - Increment `count` to 1 and set `in_word` to True.
   - Second character: `"e"` (not a space, `in_word` is True):
     - Continue.
   - Space encountered:
     - Set `in_word` to False.
   - Repeat for all characters.
4. **Final Count:**
   - Return `count = 2`.

### Code Walkthrough (Built-in Functions)
1. **Input String:**
   - Example: `"Python programming is fun."`
2. **Split Operation:**
   - `s.split()` results in `['Python', 'programming', 'is', 'fun.']`
3. **Count Words:**
   - `len(['Python', 'programming', 'is', 'fun.']) = 4`
4. **Return Result:**
   - Return `4`.

---

### Dry Run
#### Input:
`"Python programming is fun."`

#### Execution Steps:
| Step | Character   | `in_word` | `count` |
|------|-------------|-----------|---------|
| 1    | `P`         | True      | 1       |
| 2    | `y`         | True      | 1       |
| ...  | (Continue)  | ...       | ...     |
| 7    | Space       | False     | 1       |
| 8    | `p`         | True      | 2       |
| ...  | (Continue)  | ...       | ...     |
| End  |             |           | 4       |

**Output:** `4`

---

### Complexity Analysis

1. **Iterative Method:**
   - **Time Complexity:**
     - `O(n)` where `n` is the length of the string.
   - **Space Complexity:**
     - `O(1)` (no additional space used).

2. **Built-in Functions:**
   - **Time Complexity:**
     - `O(n)` for `split()` and `len()` operations.
   - **Space Complexity:**
     - `O(k)` where `k` is the number of words in the string.


