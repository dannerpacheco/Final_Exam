***
# 2:Minimun Falling Path Sum 
***

## Problem:

Given a square array of integers A, we want the minimum sum of a falling path through A.
A falling path starts at any element in the first row, and chooses one element from each
row. The next row's choice must be in a column that is different from the previous row's
column by at most one.
### Example 1:
    Input: [[1,2,3],[4,5,6],[7,8,9]]
    Output: 12
### Explanation:
    The possible falling paths are:
    * [1,4,7], [1,4,8], [1,5,7], [1,5,8], [1,5,9]
    * [2,4,7], [2,4,8], [2,5,7], [2,5,8], [2,5,9], [2,6,8], [2,6,9]
    * [3,5,7], [3,5,8], [3,5,9], [3,6,8], [3,6,9]
    The falling path with the smallest sum is [1,4,7], so the answer is 12.
***

## Approach:

When we saw this problem, we immediatly noticed that the use for dynamic programming would be very straightforward. We had to calculate the paths to the bottom, and if one of the paths intersects with and existing path, we just follow that one, since that should already be the best path down from that point. 

#### Recursive Definition:

This is a rough definition of the recursion:
    #Start at the second row since the sums of the first one are already there
    dp[][] = zeroes(A.lenght, A.lenght[0])
    dp[i][j] = min(top-right, top-middle, top-left) -> dp[i][j] = min(dp[i-1][j-1], dp[i-1][j], dp[i-1][j+1])

Of course we would have to watch out for the edges of the array to not go out of bounds. 
This definition should work, because we don't have to recalculate every path from the current "node" up, since the best path down has already been calculated

#### Data Structure:
    
As you can see from the recursive definition, we are planning on using a matrix of the same size of A to store all the paths. Each location in the matrix will store the best sum possible up to that "node"
