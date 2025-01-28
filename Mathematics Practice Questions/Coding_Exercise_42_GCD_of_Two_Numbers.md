# Problem Description:
# 
# You are given two integers n and m. Your task is to find the GCD of these two numbers. 
# The GCD is the largest positive integer that divides both numbers without leaving a remainder. 
# Do not use any built-in functions and do not use recursion.

# Input:
# Two integers n and m, where 1 <= n, m <= 10^9.

# Output:
# An integer representing the GCD of n and m.

# Example:
# Input: n = 48, m = 18
# Output: 6
 
# Input: n = 56, m = 98
# Output: 14

# Solution 1: Using the Euclidean Algorithm

def gcd(n, m):
    """
    Function to find the GCD of two integers without using built-in functions and recursion.

    Parameters:
    n (int): The first integer.
    m (int): The second integer.

    Returns:
    int: The GCD of n and m.
    """
    # Ensure n and m are positive
    n = abs(n)
    m = abs(m)

    # Use the Euclidean algorithm iteratively
    while m != 0:
        n, m = m, n % m  # Assign m to n and remainder of n divided by m to m

    return n  # When m becomes 0, n is the GCD

# Example Usage:
# print(gcd(48, 18))  # Output: 6
# print(gcd(56, 98))  # Output: 14

# Solution 2: Brute Force Approach

def find_gcd(n1, n2):
    """
    Function to find the GCD of two integers using a brute force approach.

    Parameters:
    n1 (int): The first integer.
    n2 (int): The second integer.

    Returns:
    int: The GCD of n1 and n2.
    """
    # Initialize gcd to 1
    gcd = 1

    # Iterate from 1 up to the minimum of n1 and n2
    for i in range(1, min(n1, n2) + 1):
        # Check if i is a common factor of both n1 and n2
        if n1 % i == 0 and n2 % i == 0:
            # Update gcd to the current common factor i
            gcd = i

    # Return the greatest common divisor (gcd)
    return gcd

# Example Usage:
# print(find_gcd(48, 18))  # Output: 6
# print(find_gcd(56, 98))  # Output: 14
