## 01. Subset Sums

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/subset-sums2234/1)

### Problem Description

**Task:** Given an array arr of integers, return the sums of all subsets in the list. Return the sums in any order.Examples:Input: arr[] = [2, 3]

#### Examples

##### Example 1

- **Output:**
```text
[0, 5, 6, 7, 11, 12, 13, 18]
```
- **Explanation:** The possible subset sums are 0 (no elements), 5, 6, 7, and their combinations.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(2^n)
- **Expected Auxiliary Space Complexity:** O(2^n)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-04-22 14:07:22
- **Status:** Correct
- **Marks:** 4

```java
// User function Template for Java//User function Template for Java
class Solution {
    public ArrayList<Integer> subsetSums(int[] arr) {
ArrayList<Integer> list=new ArrayList<>();
         sum(arr,0,0,list);
         return list;
    }
    public void sum(int[] arr,int ans, int idx,ArrayList<Integer> list){
        if(idx==arr.length){ 
            list.add(ans);
            return;
        }
        int num=arr[idx];
         sum(arr,ans,idx+1,list);
         sum(arr,ans+num,idx+1,list);
        
    } 
     
}
```

*Generated on: 24/11/2026, 05:05:00*