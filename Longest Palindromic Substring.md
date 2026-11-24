## 01. Longest Palindromic Substring

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/longest-palindrome-in-a-string1956/1)

### Problem Description

**Task:** Given a string s, return the longest palindromic substring in s. If there are multiple answers, return the one that appears first in the given string s.Examples :Input: s = "forgeeksskeegfor"

#### Examples

##### Example 1

- **Output:**
```text
ee
```
- **Explanation:** The longest palindromic substring present in the given string is "ee".

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-11-25 00:03:22
- **Status:** Correct
- **Marks:** 4

```java
class Solution {
    public String getLongestPal(String s1) {
        int[][] dp=new int[s1.length()][s1.length()];
               int max=0;
               StringBuilder sb=new StringBuilder();
               for(int i=0;i<s1.length();i++){
                   int k=0;
                   for(int j=i;j<s1.length();j++){
                       if(k==j) dp[k][j]=1;
                      else if(s1.charAt(k)==s1.charAt(j)){
                       if(j==k+1) dp[k][j]=2;
                       else if((j>0 && k<s1.length()-1 )&& dp[k+1][j-1]!=0){
                           dp[k][j]=dp[k+1][j-1]+2;
                       }
                      }
                      max=Math.max(max,dp[k][j]);
                      k++;
                   }
               }
                for(int i=0;i<s1.length();i++){
                   for(int j=0;j<s1.length();j++){
                       if(dp[i][j]==max){
                           int k=i;
                         while(k<=j){
                           char ch=s1.charAt(k);
                           sb.append(""+ch);
                           k++;
                         }
                         return sb.toString();    
                       }
                   }
               }
               return sb.toString();   
           }
       }
```

*Generated on: 25/11/2026, 00:03:49*