# Check if a String is a Palindrome

## Problem Statement

A string is considered a palindrome if it reads the same forward and backward, ignoring spaces, punctuation, and case.

### Parameters:
- `s` (str): The input string to check.

### Returns:
- A boolean value: `True` if the string is a palindrome, and `False` otherwise.

---

## Examples

### Example 1:
**Input:**
```python
s = "A man a plan a canal Panama"
```
**Output:**
```python
True
```
**Explanation:**
- After ignoring spaces, punctuation, and case, the string becomes `"amanaplanacanalpanama"`, which reads the same forward and backward.

### Example 2:
**Input:**
```python
s = "Hello, World!"
```
**Output:**
```python
False
```
**Explanation:**
- After normalization, the string becomes `"helloworld"`, which is not the same forward and backward.

---

## Solution Approaches

### Approach 1: Using String Normalization and Slicing

#### Steps to Solve:
1. **Normalize the String:**
   - Convert the string to lowercase.
   - Remove all non-alphanumeric characters.
2. **Check for Palindrome:**
   - Compare the normalized string with its reverse.

#### Code Implementation:
```python
def is_palindrome(s):
    """
    Function to check if the input string is a palindrome.

    Parameters:
    s (str): The input string to check.

    Returns:
    bool: True if the string is a palindrome, False otherwise.
    """
    # Normalize the string by converting to lowercase and removing non-alphanumeric characters
    normalized_str = ''.join(char.lower() for char in s if char.isalnum())

    # Check if the normalized string is equal to its reverse
    return normalized_str == normalized_str[::-1]
```

---

### Approach 2: Using Two Pointers

#### Steps to Solve:
1. **Normalize the String:**
   - Convert the string to lowercase.
   - Remove all non-alphanumeric characters.
2. **Two-Pointer Technique:**
   - Use two pointers, one starting from the beginning (`start`) and the other from the end (`end`) of the normalized string.
   - Compare the characters at both pointers. If they are different, return `False`.
   - Move the pointers closer to the center until they meet or cross.

#### Code Implementation:
```python
def is_palindrome(s):
    """
    Function to check if the input string is a palindrome.

    Parameters:
    s (str): The input string to check.

    Returns:
    bool: True if the string is a palindrome, False otherwise.
    """
    # Normalize the string by converting to lowercase and removing non-alphanumeric characters
    s = ''.join(char.lower() for char in s if char.isalnum())

    # Initialize two pointers
    start = 0
    end = len(s) - 1

    # Use two pointers to check for palindrome
    while start < end:
        if s[start] != s[end]:
            return False
        start += 1
        end -= 1

    return True
```

---

### Code Walkthrough

#### Example Input:
`"A man a plan a canal Panama"`

1. **Normalization:**
   - Convert to lowercase: `"a man a plan a canal panama"`
   - Remove non-alphanumeric characters: `"amanaplanacanalpanama"`

2. **Two Pointers:**
   - Start at the beginning (`start = 0`) and end at the last character (`end = len(s) - 1`).
   - Compare characters:
     - `s[0] == s[-1]` -> `True`
     - Move pointers inward and repeat until `start >= end`.

3. **Output:**
   - All characters match; return `True`.

---

### Complexity Analysis

#### Time Complexity:
- **Normalization:** O(n), where `n` is the length of the string.
- **Palindrome Check:** O(n/2) = O(n).
- **Overall:** O(n).

#### Space Complexity:
- **Normalization:** O(n), as we store the normalized string.
- **Two-Pointer Variables:** O(1).
- **Overall:** O(n).

---

Feel free to test the function with various edge cases, such as strings containing special characters, spaces, and different cases, to ensure its robustness! 🚀
