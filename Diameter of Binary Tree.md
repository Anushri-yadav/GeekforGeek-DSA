## 01. Diameter of Binary Tree

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/diameter-of-binary-tree/1)

### Problem Description

**Task:** My SubmissionsRefresh

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** Not found
- **Expected Auxiliary Space Complexity:** Not found

### Accepted Solutions (2)

#### Solution 1 (Java)

- **Submitted:** 2026-11-27 01:27:28
- **Status:** Correct
- **Marks:** 0

```java
/*Structure of binary tree Node
class Node {
    int data;
    Node left;
    Node right;
    Node(int data) {
        this.data = data;
        left = right = null;
    }
};*/

class Solution {
    int maxdia=0;
    public int diameter(Node root) {
HashMap<Node,Integer> dp=new HashMap<>();
       level(root,dp);
       return maxdia;
    }
    int level(Node root,HashMap<Node,Integer> dp){
        if(root==null) return 0;
        if(dp.containsKey(root)) return dp.get(root);
        int left=level(root.left,dp);
        int right=level(root.right,dp);
        maxdia=Math.max(maxdia,left+right);
        int height=1+Math.max(left,right);
        dp.put(root,height);
        return height;
    }
}
```

#### Solution 2 (Java)

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

*Generated on: 27/11/2026, 01:27:56*