## 01. Rat in Maze

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/rat-in-a-maze-problem/1)

### Problem Description

**Task:** Given a square binary matrix maze[][] containing values 0 and 1, find all possible paths for a rat to travel from the top-left cell to the bottom-right cell. The rat can move in four directions: up(U), down(D), left(L), and right(R).1 represents an open cell through which the rat can move.0 represents a blocked cell that cannot be traversed.The rat can move only through open cells and cannot visit the same cell more than once in a path. Return all valid paths as strings consisting of 'U', 'D', 'L', and 'R', representing the sequence of moves taken by the rat.Note: Return the paths in lexicographically increasing order. If no valid path exists, return an empty list.Examples:Input: maze[][] = [[1, 0, 0, 0], [1, 1, 0, 1], [1, 1, 0, 0], [0, 1, 1, 1]]

#### Examples

##### Example 1

- **Output:**
```text
[]
```
- **Explanation:** No path exists as the destination cell (1, 1) is blocked.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(4 ^ (n * n))
- **Expected Auxiliary Space Complexity:** O(n * n)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-11-28 20:01:56
- **Status:** Correct
- **Marks:** 4

```java
class Solution {
    public ArrayList<String> ratInMaze(int[][] maze) {
        int m=maze.length;
        int n=maze[0].length;
        ArrayList<String> list=new ArrayList<>();
        rat(0,0,m-1,n-1,"",list,maze);
        return list;
    }
    void rat(int i,int j,int m,int n,String s,ArrayList<String> list,int[][] maze){
        if(i>m || j>n || i<0 || j<0) return;
        if(maze[i][j]==0) return;
        if(i==m && j==n){
            list.add(s);
            return;
        }
        maze[i][j]=0;
        rat(i+1,j,m,n,s+"D",list,maze);
        rat(i,j-1,m,n,s+"L",list,maze);
        rat(i,j+1,m,n,s+"R",list,maze);
        rat(i-1,j,m,n,s+"U",list,maze);
        maze[i][j]=1;
    }
}
```

*Generated on: 28/11/2026, 20:02:26*