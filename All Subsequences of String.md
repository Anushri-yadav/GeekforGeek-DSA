## 01. All Subsequences of String

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/power-set4302/1)

### Problem Description

**Task:** Given a string s, generate all possible subsequences of the string (including the empty subsequence) and return them in lexicographical order.A subsequence is obtained by deleting zero or more characters from the string without changing the relative order of the remaining characters.Examples:Input : s = "abc"

#### Examples

##### Example 1

- **Output:**
```text
["", "a", "a", "aa"]
```
- **Explanation:** There are a total of 8 non-empty subsequences for the given string. Input: s = "aa"

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n*(2^n))
- **Expected Auxiliary Space Complexity:** O(n*(2^n))

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-04-22 14:03:04
- **Status:** Correct
- **Marks:** 4

```java
// User function Template for Java

class Solution {
    public List<String> AllPossibleStrings(String s) {
       ArrayList<String> list=new ArrayList<>();
        string(s,"",0,list);
        Collections.sort(list);
        return list;
    }
    public void string(String s, String ans,int idx,ArrayList<String> list){
        if(idx==s.length()){
            if(ans.length()!=0){
          list.add(ans);  
            }
        return;
        } 
        char ch=s.charAt(idx);
        string(s,ans,idx+1,list);
        string(s,ans+ch,idx+1,list);
        
    }
}
```

*Generated on: 24/11/2026, 05:04:23*