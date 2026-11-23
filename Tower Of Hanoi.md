## 01. Tower Of Hanoi

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/tower-of-hanoi-1587115621/1)

### Problem Description

**Task:** Given n disks, consider three rods: the starting rod(from), the target rod (to), and an auxiliary rod (aux). Initially disks are placed on the starting rod. The smallest disk is placed on top and the largest at the bottom. Calculate the minimum number of moves required to transfer all n disks from the starting rod to the target rod, following these rules:Only one disk can be moved at a time.A disk can only be placed on top of a larger disk or on an empty rod.Find the minimum number of moves needed to complete the task.Examples:Input: n = 2

#### Examples

##### Example 1

- **Output:**
```text
0
```
- **Explanation:** Total 0 steps will be taken.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(2^n)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-04-22 22:07:07
- **Status:** Correct
- **Marks:** 4

```java
class Solution {
    public int towerOfHanoi(int n, int from, int to, int aux) {
        // code here
        return (int)(Math.pow(2,n)-1);
    }
}
```

*Generated on: 24/11/2026, 05:07:26*