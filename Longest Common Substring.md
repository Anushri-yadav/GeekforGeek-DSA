## 01. Longest Common Substring

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/longest-common-substring1452/1)

### Problem Description

**Task:** Given two strings s1 and s2, determine the length of the longest substring that appears in both strings.Examples:Input: s1 = "ABCDGH", s2 = "ACDGHR"

#### Examples

##### Example 1

- **Output:**
```text
4
```
- **Explanation:** The longest common substring is "CDGH" with a length of 4.

##### Example 2

- **Input:**
```text
s1 = "abc", s2 = "acb"
```
- **Output:**
```text
1
```
- **Explanation:** The longest common substrings are "a", "b", "c" all having length 1.

##### Example 3

- **Input:**
```text
s1 = "YZ", s2 = "yz"
```
- **Output:**
```text
0Explanation: Comparison is case-sensitive, so 'Y' ≠ 'y' and 'Z' ≠ 'z'. Hence, no common substring exists.
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n * m)
- **Expected Auxiliary Space Complexity:** O(n * m)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-11-24 22:05:15
- **Status:** Correct
- **Marks:** 4

```java
class Solution {
    public int longCommSubstr(String s1, String s2) {
        int[][] dp=new int[s1.length()][s2.length()];
        int max=0;
        for(int i=0;i<s1.length();i++){
            for(int j=0;j<s2.length();j++){
                if(s1.charAt(i)==s2.charAt(j)){
                  if(i==0 || j==0) dp[i][j]=1;
                  else dp[i][j]=1+dp[i-1][j-1];
                }
                else dp[i][j]=0;
                max=Math.max(max,dp[i][j]);
            }
        }
        return max;
    }
}
```

*Generated on: 24/11/2026, 22:05:54*