## 01. Smallest Divisor

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/smallest-divisor/1)

### Problem Description

**Task:** Given an integer array arr[] and an integer k (where k ≥ arr.length), find the smallest positive integer divisor such that the sum of the ceiling values of each element in arr[] divided by this divisor is less than or equal to k.Examples:Input: arr[] = [1, 2, 5, 9], k = 6

#### Examples

##### Example 1

- **Output:**
```text
1Explanation: 1 is the smallest divisor having sum of quotients (1 + 1 + 1 + 1 = 4) less than or equal to 4.
```
- **Explanation:** 5 is the smallest divisor having sum of quotients (1 + 1 + 1 + 2 = 5) less than or equal to 6.Input: arr[] = [1, 1, 1, 1], k = 4

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n * log(max(arr[i])))
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-11-28 02:53:03
- **Status:** Correct
- **Marks:** 4

```java
class Solution {
    int smallestDivisor(int[] nums, int thr) {
       int max=0;
               int sum=0;
              for(int i=0;i<nums.length;i++){
               max=Math.max(max,nums[i]);
               sum+=nums[i];
              }
              int lo=sum/thr;
              if(lo==0) lo=1;
              int hi=max;
              while(lo<hi){
               int mid=lo+(hi-lo)/2;
               if(divisor(mid,nums)<=thr) hi=mid;
               else lo=mid+1;
              }
              return lo;
           }
           int divisor(int mid,int[] arr){
               int sum=0;
              for(int i=0;i<arr.length;i++){
               sum=sum+(arr[i] + mid - 1) / mid;
              }
              return sum;
           }
       }
```

*Generated on: 28/11/2026, 02:53:32*