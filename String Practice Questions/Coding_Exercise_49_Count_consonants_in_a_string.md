# Count Consonants in a String

## Problem Statement

Design a Python function named `count_consonants` to count the number of consonants in a given string. A consonant is defined as any alphabetic character that is not a vowel (a, e, i, o, u).

### Parameters:
- `s` (str): The input string in which you need to count the consonants. The length of `s` is between 1 and 1000.

### Returns:
- An integer representing the total number of consonants in the input string.

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
- The consonants in the string are `H`, `l`, `l`, `W`, `r`, `l`, and `d`. Hence, the total count is 7.

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
- The consonants in the string are `P`, `y`, `t`, `h`, `n`, `P`, `r`, `g`, `r`, `m`, `m`, `n`, and `g`. Hence, the total count is 13.

---

## Solution Approach

### Steps to Solve:
1. **Identify Consonants:**
   - A consonant is an alphabetic character that is not a vowel (`a, e, i, o, u`).
   - Use the `isalpha()` method to check if a character is alphabetic.
   - Exclude vowels by checking if the character is not in the defined set of vowels.
2. **Iterate Through the String:**
   - Loop through each character in the input string.
   - Check if the character is a consonant using the conditions defined above.
3. **Count Consonants:**
   - Increment a counter for each consonant found in the string.
4. **Return the Count:**
   - Return the total count of consonants after the loop.

---

### Code Implementation
```python
def count_consonants(s):
    """
    Function to count the number of consonants in the input string.

    Parameters:
    s (str): The input string to check for consonants.

    Returns:
    int: The count of consonants in the input string.
    """
    vowels = "aeiouAEIOU"  # Define the set of vowels (both uppercase and lowercase)
    count = 0  # Initialize a counter for consonants

    # Loop through each character in the string
    for char in s:
        # Check if the character is an alphabet and not a vowel
        if char.isalpha() and char not in vowels:
            count += 1  # Increment the count if it is a consonant

    return count
```

---

### Code Walkthrough
1. **Initialization:**
   - Define `vowels` as a string containing both lowercase and uppercase vowels.
   - Initialize `count` to 0.

2. **Iterate Through the String:**
   - For each character `char` in the input string:
     - Check if `char` is an alphabet using `isalpha()`.
     - Check if `char` is not in `vowels`.
     - If both conditions are true, increment the `count`.

3. **Return the Count:**
   - After the loop, return the final value of `count`.

---

### Dry Run

#### Input:
`s = "Hello, World!"`

#### Execution Steps:
| Step | Character | Is Alphabet? | Is Not a Vowel? | Consonant Count |
|------|-----------|--------------|-----------------|-----------------|
| 1    | `H`       | Yes          | Yes             | 1               |
| 2    | `e`       | Yes          | No              | 1               |
| 3    | `l`       | Yes          | Yes             | 2               |
| 4    | `l`       | Yes          | Yes             | 3               |
| 5    | `o`       | Yes          | No              | 3               |
| 6    | `,`       | No           | -               | 3               |
| 7    | ` `       | No           | -               | 3               |
| 8    | `W`       | Yes          | Yes             | 4               |
| 9    | `o`       | Yes          | No              | 4               |
| 10   | `r`       | Yes          | Yes             | 5               |
| 11   | `l`       | Yes          | Yes             | 6               |
| 12   | `d`       | Yes          | Yes             | 7               |
| 13   | `!`       | No           | -               | 7               |

**Output:** `7`

---

### Complexity Analysis

1. **Time Complexity:**
   - The function iterates through each character in the input string, making it **O(n)**, where `n` is the length of the string.

2. **Space Complexity:**
   - The space usage is constant, **O(1)**, as no additional data structures are used.

