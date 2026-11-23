## 01. Subset Sum Problem

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/subset-sum-problem-1611555638/1)

### Problem Description

**Task:** Given an array of positive integers arr[] and a value sum, find if there is a subset of arr[] with sum equal to given sum. Examples:Input: arr[] = [3, 34, 4, 12, 5, 2], sum = 9Output: true

#### Examples

##### Example 1

- **Explanation:** Here there exists a subset with target sum = 9, 4+3+2 = 9.

##### Example 2

- **Input:**
```text
arr[] = [3, 34, 4, 12, 5, 2], sum = 30
```
- **Output:**
```text
trueExplanation: The entire array can be taken as a subset, giving 1 + 2 + 3 = 6.
```
- **Explanation:** There is no subset with target sum 30.Input: arr[] = [1, 2, 3], sum = 6

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(sum*n)
- **Expected Auxiliary Space Complexity:** O(sum)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-11-10 00:24:15
- **Status:** Correct
- **Marks:** 4

```java
class Solution {
    static boolean isSubsetSum(int arr[], int sum) {
        int[][] dp=new int[arr.length][sum+1];
        for(int[] i: dp){
            Arrays.fill(i,-1);
        }
        return loot(0,sum,arr,dp);
    }
   static boolean loot(int i,int sum,int[] arr,int[][] dp){
        if(i==arr.length ){
          if(sum==0) return true;
            else return false;
        } 
        if(dp[i][sum]!=-1){
            if(dp[i][sum]==1) return true;
            else return false;
        }
        boolean ans =false;
        boolean skip=loot(i+1,sum,arr,dp);
        if(arr[i]>sum) ans=skip;
        else{
           boolean pick=loot(i+1,sum-arr[i],arr,dp);
           ans=pick || skip;
        }
        if(ans) dp[i][sum]=1;
        else dp[i][sum]=0;
        return ans;
    }
}
```

*Generated on: 24/11/2026, 04:37:22*