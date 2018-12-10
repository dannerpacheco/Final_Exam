***
# 4:Arithmetic Slices
***

## Problem:

A sequence of number is called arithmetic if it consists of at least three elements and if the difference between any two consecutive elements is the same.

For example, these are arithmetic sequence:

    1, 3, 5, 7, 9
    7, 7, 7, 7
    3, -1, -5, -9

The following sequence is not arithmetic.

    1, 1, 2, 5, 7

A zero-indexed array A consisting of N numbers is given. A slice of that array is any pair of integers (P, Q) such that 0 <= P < Q < N.

A slice (P, Q) of array A is called arithmetic if the sequence: A[P], A[p + 1], ..., A[Q - 1], A[Q] is arithmetic. In particular, this means that P + 1 < Q.

The function should return the number of arithmetic slices in the array A.

### Example:

Input: [1, 2, 3, 4]
Output: 3, for 3 arithmetic slices in A: [1, 2, 3], [2, 3, 4] and [1, 2, 3, 4] itself. 


***

## Approach:

Assuming we already have solutions for a bigger part of the problem really helped visualise the answer for this particular problem. We can store solutions for every subset of the array, and refer back to them to compute further subsets. 

#### Recursive Definition:

if differences between i, i+1, and i+2 are the same
    dp[i] = 2 * dp[i - 1] - dp[i - 2] + 1


#### Data Structure:

Two arrays will be used, one to store the number of slices and another one to store the differences. 
