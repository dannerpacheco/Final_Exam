***
# 5:Minimun ASCII Delete Sum
***

## Problem:

Given two strings s1, s2, find the lowest ASCII sum of deleted characters to make two strings equal.

### Example 1:

    Input: s1 = "sea", s2 = "eat"
    Output: 231
    Explanation: Deleting "s" from "sea" adds the ASCII value of "s" (115) to the sum.
    Deleting "t" from "eat" adds 116 to the sum.
    At the end, both strings are equal, and 115 + 116 = 231 is the minimum sum possible to achieve this.

### Example 2:

    Input: s1 = "delete", s2 = "leet"
    Output: 403
    Explanation: Deleting "dee" from "delete" to turn the string into "let",
    adds 100[d]+101[e]+101[e] to the sum.  Deleting "e" from "leet" adds 101[e] to the sum.
    At the end, both strings are equal to "let", and the answer is 100+101+101+101 = 403.
    If instead we turned both strings into "lee" or "eet", we would get answers of 433 or 417, which are higher.

***

## Approach:

Once again, instead of having to compute all the possible combination of values to edit the string, we can store the sum up to a character in a string, and work our way backwards. 

#### Recursive Definition:

First fill the last row and last column of the matrix with the sum of the characters in the string going from last to first. 

Then fill the matrix from the bottom right to the top left:

if characters at i and j are the same:
    dp[i][j] = dp[i+1][j+1]
else
    dp[i][j] = min(dp[i][j+1] + char at j, dp[i+1][j] char at i)


The sum will be at the first index of the matrix

#### Data Structure:
    
For this problem we will use a matrix
