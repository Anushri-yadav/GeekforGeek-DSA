## 01. Matrix Chain Multiplication

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/matrix-chain-multiplication0303/1)

### Problem Description

**Task:** Given an array arr[] which represents the dimensions of a sequence of matrices where the i^th matrix has the dimensions (arr[i-1] x arr[i]) for i >= 1, find the most efficient way to multiply these matrices together. The efficient way is the one that involves the least number of multiplications.Examples:Input: arr[] = [2, 1, 3, 4]

#### Examples

##### Example 1

- **Output:**
```text
0Explanation: As there is only one matrix so, there is no cost of multiplication.
```
- **Explanation:** There are 4 matrices of dimensions 1 × 2, 2 × 3, 3 × 4, 4 × 3. Let this 4 input matrices be M1, M2, M3 and M4. The minimum number of multiplications are obtained by ((M1 x M2) x M3) x M4). The minimum number is (1 x 2 x 3) + (1 x 3 x 4) + (1 x 4 x 3) = 30.Input: arr[] = [3, 4]

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n^3)
- **Expected Auxiliary Space Complexity:** O(n^2)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-11-27 13:55:19
- **Status:** Correct
- **Marks:** 8

```java
class Solution {
    static int matrixMultiplication(int arr[]) {
        int n = arr.length;
        int dp[][] = new int[n][n];
        for(int row[] : dp) Arrays.fill(row, -1);
        return cost(0,arr.length-2,arr,dp);
    }
    static int cost(int i,int j,int[] arr,int[][] dp){
        if(i==j) return 0;
        if(dp[i][j]!=-1) return dp[i][j];
        int mincost=Integer.MAX_VALUE;
        for(int k=i;k<j;k++){
            int x=arr[i]*arr[k+1]*arr[j+1];
            int tc=cost(i,k,arr,dp)+cost(k+1,j,arr,dp)+x;
            mincost= Math.min(mincost,tc);
        }
        return dp[i][j]=mincost;
    }
}
```

*Generated on: 27/11/2026, 13:55:47*