## 01. 💡 Diameter of a Binary Tree (C++)

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/diameter-of-binary-tree/1)

### Problem Description

**Task:** Given the root of a binary tree, find the diameter of the binary tree. The diameter of a binary tree is defined as the number of edges on the longest path between any two nodes. Note that this path may or may not pass through the root of the tree.Examples:Input: root = [1, 2, N, 3, 4]Output: 2Explanation: The longest path has 2 edges (node 3 - > node 2 - > node 4).Input: root = [5, 8, 6, 3, 7, 9, N]Output: 4Explanation: The longest path has 4 edges (node 3 - > node 8 - > node 5 - > node 6 - > node 9).

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(h)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-06-26 17:38:40
- **Status:** Correct
- **Marks:** 4

```java
/*
Definition for Node
class Node {
    int data;
    Node left;
    Node right;
    Node(int data) {
        this.data = data;
        left = right = null;
    }
} */

class Solution {
    static int max;
    public int diameter(Node root) {
         max=0;
        level(root);
        return max;
    }
    int level(Node root){
        if(root ==null) return 0;
        int leftlevel=level(root.left);
        int rightlevel=level(root.right);
        max=Math.max(max,leftlevel+rightlevel);
        return 1+Math.max(leftlevel,rightlevel);
    }
}
```

*Generated on: 27/11/2026, 01:24:19*