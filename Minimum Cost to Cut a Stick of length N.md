## 01. Minimum Cost to Cut a Stick of length N

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/minimum-cost-to-cut-a-stick-of-length-n/1)

### Problem Description

**Task:** You are given a wooden stick of length n, labeled from 0 to n. You are also given an integer array cuts[], where each element cuts[i] represents a position along the stick at which you can make a cut.Each cut costs an amount equal to the length of the stick being cut at that moment. After performing a cut, the stick is divided into two smaller sticks.You can perform the cuts in any order. Your task is to determine the minimum total cost required to perform all the cuts.Example:Input: n = 10, cuts[] = [2, 4, 7]Output: 20Explanation: If we cut the stick in the order [4, 2, 7], the cost will be 10 + 4 + 6 = 20, which is the minimum total cost.Input: n = 8, cuts[] = [1, 6, 3, 5]Output: 19Explanation: If we cut the stick in the order [3, 6, 1, 5], the cost will be 8 + 5 + 3 + 3 = 19, which is the minimum total cost.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(m^3),  m = cuts.size()
- **Expected Auxiliary Space Complexity:** O(m^2)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-11-27 19:31:38
- **Status:** Correct
- **Marks:** 8

```java
class Solution {
    public int minCutCost(int n, int[] cuts) {
     int [][] dp=new int[cuts.length+1][cuts.length+1];
            for(int[] row:dp){
                Arrays.fill(row,-1);
            }
            int arr[]=new int[cuts.length+2];
            arr[0]=0;
            arr[cuts.length+1]=n;
            for(int i=0;i<cuts.length;i++){
                arr[i+1]=cuts[i];
            }
            Arrays.sort(arr);
            return cost(1,cuts.length,arr,dp);
        }
        int cost(int i,int j,int[] arr,int[][] dp){
            if(i>j) return 0;
            if(dp[i][j]!=-1) return dp[i][j];
            int min=Integer.MAX_VALUE;
            for(int k=i;k<=j;k++){
                int len=arr[j+1]-arr[i-1];
                int totalcost=cost(i,k-1,arr,dp)+cost(k+1,j,arr,dp)+len;
                min = Math.min(min,totalcost);
            }
            return dp[i][j]=min;
        }
    }
```

*Generated on: 27/11/2026, 19:32:03*