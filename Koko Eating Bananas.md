## 01. Koko Eating Bananas

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/koko-eating-bananas/1)

### Problem Description

**Task:** Koko is given an array arr[], where each element represents a pile of bananas. She has exactly k hours to eat all the bananas.Each hour, Koko can choose one pile and eat up to s bananas from it.If the pile has atleast s bananas, she eats exactly s bananas.If the pile has fewer than s bananas, she eats the entire pile in that hour. Koko can only eat from one pile per hour. Your task is to find the minimum value of s (bananas per hour) such that Koko can finish all the piles within k hours.Examples:Input: arr[] = [5, 10, 3], k = 4

#### Examples

##### Example 1

- **Output:**
```text
10
```
- **Explanation:** If Koko eats at the rate of 10 bananas per hour, it will take 6 hours to finish all the piles.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n * log(max(arr[i])))
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-11-28 01:24:57
- **Status:** Correct
- **Marks:** 4

```java
class Solution {
    public int kokoEat(int[] piles, int h) {
         int max=0;
              for(int i=0;i<piles.length;i++){
                max=Math.max(max,piles[i]);
              } 
              int lo=1;
              int hi=max;
              while(lo<hi){
                int mid=lo+(hi-lo)/2;
                if(hour(mid,piles)<=h){
                    hi=mid;
                }
                else{
                    lo=mid+1;
                }
              } 
              return lo;
            }
            int hour(int cap, int[] arr){
                    int h = 0;

                    for(int i = 0; i < arr.length; i++){
                        h += (arr[i] + cap - 1) / cap;
                    }

                    return h;
                }
        }
```

*Generated on: 28/11/2026, 01:25:25*