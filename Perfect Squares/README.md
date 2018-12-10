***
# 9: Perfect Squares
***

## Problem:

Given a positive integer n, find the least number of perfect square numbers (for example, 1, 4, 9, 16, ...) which sum to n.

### Example 1

    Input: n = 12
    Output: 3 

### Example 2

    Input: n = 13
    Output: 2

***

## Approach:

While using the naive approach would take too long to compute, this problem can be solved faster if we use dynamic programming. We can keep an array that will store the local minimun number and then compare that to the already stores mins. 

#### Recursive Definition:

Create two loops, outside loop goes up to n one by one, inside finds the squares.

min = min(min, dp[i-j*j] + 1)

#### Data Structure:

For this problem we dould only need an array and a variable to store the local min. 