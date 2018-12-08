***
# 3: Palindromic Substrings
***

## Problem:

Given a string, your task is to count how many palindromic substrings in this string.
The substrings with different start indexes or end indexes are counted as different substrings even they consist of same characters.

### Example 1:

    Input: "abc"
    Output: 3
    Explanation: Three palindromic strings: "a", "b", "c".

### Example 2:

    Input: "aaa"
    Output: 6
    Explanation: Six palindromic strings: "a", "a", "a", "aa", "aa", "aaa".

#### Note:

    The input string length won't exceed 1000.

***

## Approach:

It took a little while to come up with a solution, but thanks to the professor's help, we had a basis for the problem. We could use a matrix. The matrix stores which indexes are palindromes, for example, matrix[0][4] would indicate if the string formed with characters 1-5 is a palindrome. The logic is that we first check the small substrings, and then, to check if a larger string is a palindrome, we just have to check if the string inside that string is a palyndrome, and if the characters at the edges are the same. 


#### Recursive Definition:
Initially the matrix would all be set to -1 to indicate that an answer has not been found, the diagonal is set to 1. In that case,the answer has to be found manually. We first start with substrings of lenght 1, then 2, 3, 4, and so on. 

```python
if dp_matrix[i+1][j-1] == 1:
    if string[i] == string[j]:
        dp_matrix[i][j] = 1
    else:
        dp_matrix[i][j] = 0
else:
    dp_matrix[i][j] = 0 
```

#### Data Structure:

As mentioned above, we would use a matrix to store the previously computed palyndromes. In the end, we would need to count the number of ones in half the matrix split by the diagonal, plus the ones in the diagonal. 
    
