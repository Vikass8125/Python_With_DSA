# Check Subsequence

## Problem Statement

You are given two strings `s` and `t`. Your task is to determine if string `t` is a subsequence of string `s`. A subsequence of a string is a new string that is formed from the original string by deleting some (or no) characters without changing the order of the remaining characters.

### Parameters:
- `s` (str): The original string.
- `t` (str): The target subsequence string.

### Returns:
- A boolean value, `True` if `t` is a subsequence of `s`, and `False` otherwise.

---

## Examples

### Example 1:
**Input:**
```python
s = "abcde"
t = "ace"
```

**Output:**
```python
True
```

**Explanation:**
- By deleting the characters `b` and `d` from the string `s`, we get the subsequence `ace`, which matches string `t`.

### Example 2:
**Input:**
```python
s = "abcde"
t = "aec"
```

**Output:**
```python
False
```

**Explanation:**
- The order of characters in `t` ("aec") cannot be obtained by deleting characters from `s` without rearranging them. Hence, `t` is not a subsequence of `s`.

---

## Solution Approach

### Brute Force Solution

The brute force approach involves checking all possible subsequences of `s` to see if any of them matches `t`. This approach is inefficient as it involves generating all possible subsequences, which grows exponentially with the length of `s`.

#### Code Implementation:
```python
def is_subsequence_brute_force(s, t):
    """
    Check if t is a subsequence of s using a brute force approach.

    Parameters:
    s (str): The original string.
    t (str): The target subsequence string.

    Returns:
    bool: True if t is a subsequence of s, False otherwise.
    """
    def generate_subsequences(s):
        if not s:
            return [""]
        smaller_subsequences = generate_subsequences(s[1:])
        return smaller_subsequences + [s[0] + sub for sub in smaller_subsequences]

    subsequences_of_s = generate_subsequences(s)
    return t in subsequences_of_s
```

#### Complexity Analysis:
- **Time Complexity:** Exponential, as it involves generating all subsequences.
- **Space Complexity:** Exponential, due to the storage of subsequences.

---

### Optimal Solution

The optimal solution uses two pointers to efficiently check if `t` is a subsequence of `s`.

#### Steps to Solve:
1. Initialize two pointers:
   - `i` for traversing string `s`.
   - `j` for traversing string `t`.
2. Loop through `s` using the `i` pointer:
   - If `s[i] == t[j]`, increment the `j` pointer to check the next character in `t`.
   - Always increment the `i` pointer to traverse `s`.
3. After the loop, if `j` equals the length of `t`, it means all characters of `t` have been matched in order in `s`.

#### Code Implementation:
```python
def is_subsequence(s, t):
    """
    Check if t is a subsequence of s using an optimal two-pointer approach.

    Parameters:
    s (str): The original string.
    t (str): The target subsequence string.

    Returns:
    bool: True if t is a subsequence of s, False otherwise.
    """
    i, j = 0, 0  # Initialize two pointers

    while i < len(s) and j < len(t):
        if s[i] == t[j]:  # Match found
            j += 1
        i += 1

    return j == len(t)
```

---

## Code Walkthrough

1. **Initialization:**
   - Start with pointers `i = 0` and `j = 0`.

2. **Traversing the Strings:**
   - Compare `s[i]` and `t[j]`.
   - If they match, move to the next character in `t` by incrementing `j`.
   - Always move to the next character in `s` by incrementing `i`.

3. **Final Check:**
   - If `j == len(t)`, it means all characters in `t` have been matched in `s` in the correct order.

#### Dry Run:
**Input:**
```python
s = "abcde"
t = "ace"
```

**Execution Steps:**
| Step | i | j | s[i] | t[j] | Match? | Action         |
|------|---|---|-------|-------|--------|----------------|
| 1    | 0 | 0 | a     | a     | Yes    | Increment j, i |
| 2    | 1 | 1 | b     | c     | No     | Increment i    |
| 3    | 2 | 1 | c     | c     | Yes    | Increment j, i |
| 4    | 3 | 2 | d     | e     | No     | Increment i    |
| 5    | 4 | 2 | e     | e     | Yes    | Increment j, i |
| 6    | 5 | 3 | -     | -     | -      | End Loop       |

**Output:**
```python
True
```

---

### Complexity Analysis

1. **Time Complexity:**
   - The loop traverses `s` once, making it **O(n)**, where `n` is the length of `s`.

2. **Space Complexity:**
   - No additional space is used other than pointers, making it **O(1)**.

---
