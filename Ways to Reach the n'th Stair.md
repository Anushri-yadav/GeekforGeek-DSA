## 01. Ways to Reach the n'th Stair

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/count-ways-to-reach-the-nth-stair-1587115620/1)

### Problem Description

**Task:** There are n stairs, a person standing at the bottom wants to reach the top. The person can climb either 1 stair or 2 stairs at a time. Count the number of ways, the person can reach the top (order does matter). Examples:Input: n = 1

#### Examples

##### Example 1

- **Output:**
```text
5
```
- **Explanation:** There are five ways to reach 4th stair: [1, 1, 1, 1], [1, 1, 2], [2, 1, 1], [1, 2, 1] and [2, 2].

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-04-21 19:51:11
- **Status:** Correct
- **Marks:** 4

```java
class Solution {
    int countWays(int n) {
        // your code here
        if(n==1 || n==2) return n;
      return countWays(n-1) + countWays(n-2);  
    }
}
```

*Generated on: 24/11/2026, 05:00:47*