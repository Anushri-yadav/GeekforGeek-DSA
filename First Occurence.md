## 01. First Occurence

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/implement-strstr/1)

### Problem Description

**Task:** Given two strings txt and pat, return the 0-based index of the first occurrence of the substring pat in txt. If pat is not found, return -1.Examples :Input: txt = "GeeksForGeeks", pat = "Fr"

#### Examples

##### Example 1

- **Output:**
```text
-1
```
- **Explanation:** "gr" is not present in the string "GeeksForGeeks" as substring.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n^2)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-04-22 10:08:59
- **Status:** Correct
- **Marks:** 1

```java
class Solution {
    int firstOccurence(String txt, String pat) {
        // code here
        return sstring(txt, pat, 0);
    }
    int sstring(String txt, String pat, int index){
       int n=pat.length();
        if(txt.length()<n) return -1;
        if(txt.substring(0,n).equals(pat)) return index;
      return sstring(txt.substring(1) ,pat, index+1); 
    }
}
```

*Generated on: 24/11/2026, 05:01:16*