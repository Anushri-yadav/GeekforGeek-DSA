## 01. Unique BSTs

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/unique-bsts-1587115621/1)

### Problem Description

**Task:** Given an integer n. Find how many structurally unique binary search trees are there that stores the values from 1 to n (inclusive). Examples:Input: n = 2

#### Examples

##### Example 1

- **Output:**
```text
2
```
- **Explanation:** for n = 2, there are 2 unique BSTs

##### Example 2

- **Input:**
```text
n = 3Output: 5Explanation: for n = 3, there are 5 possible BSTs
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n^2)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-11-25 02:53:35
- **Status:** Correct
- **Marks:** 4

```java
class Solution {
    static int numTrees(int n) {
        int dp[]=new int[n+1];
              dp[0]=1;
              dp[1]=1;
              for(int i=2;i<n+1;i++){
                   int k=0;
                   int z=i-1;
                   int sum=0;
                   while(z>=0 && k<i){
                       sum=sum +dp[z]*dp[k];
                       k++;
                       z--;
                   }
                   dp[i]=sum;
              } 
              return dp[n];
           }
       }
```

*Generated on: 25/11/2026, 02:53:58*