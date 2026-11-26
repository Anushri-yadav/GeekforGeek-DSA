## 01. Maximum Path Sum

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/maximum-path-sum-from-any-node/1)

### Problem Description

**Task:** Given the root of a binary tree, find the maximum path sum. The path may start and end at any node in the tree.

#### Examples

##### Example 1

- **Input:**
```text
root[] = [10, 2, 10, 20, 1, N, -25, N, N, N, N, 3, 4]
```
- **Output:**
```text
42
```
- **Explanation:** Max path sum is represented using green colored nodes in the above binary tree.

##### Example 2

- **Input:**
```text
root[] = [-17, 11, 4, 20, -2, 10]
```
- **Output:**
```text
31
```
- **Explanation:** Max path sum is represented using green colored nodes in the above binary tree.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(h)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-11-27 02:44:22
- **Status:** Correct
- **Marks:** 4

```java
/* Structure of binary tree node
class Node{
    int data;
    Node left, right;
    Node(int val){
        data = val;
        left = right = null;
    }
}*/

class Solution {
    int maxdia=Integer.MIN_VALUE;
    int findMaxSum(Node root) {
       HashMap<Node,Integer> dp=new HashMap<>();
             level(root,dp);
             return maxdia;
          }
          int level(Node root,HashMap<Node,Integer> dp){
              if(root==null) return 0;
              if(dp.containsKey(root)) return dp.get(root);
              int left = Math.max(0, level(root.left, dp));
              int right = Math.max(0, level(root.right, dp));
              maxdia=Math.max(maxdia,left+right+root.data);
              int height=root.data+Math.max(left,right);
              dp.put(root,height);
              return height;
          }
      }
```

*Generated on: 27/11/2026, 02:44:50*