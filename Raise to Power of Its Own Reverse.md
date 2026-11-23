## 01. Raise to Power of Its Own Reverse

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/power-of-numbers-1587115620/1)

### Problem Description

**Task:** Given a number n, find the value of n raised to the power of its own reverse. The result will always fit into a 32-bit signed integer.Examples:Input: n = 2Output: 4

#### Examples

##### Example 1

- **Output:**
```text
10
```
- **Explanation:** The reverse of 10 is 1 (leading zero is discarded), and 10 raised to the power 1 is 10.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(log n)
- **Expected Auxiliary Space Complexity:** O(log n)

### Accepted Solutions (2)

#### Solution 1 (Java)

- **Submitted:** 2026-04-21 11:28:46
- **Status:** Correct
- **Marks:** 0

```java
class Solution {
    public int reverseExponentiation(int n) {
        // code here
       int val=0; 
       int ans=0;
       int num=n;
    while(num>0){
      val=num%10;
      num=num/10;
      ans=ans*10+val;
    }
    int ans2=pow(n,ans/2);
    if(ans%2!=0){
      return ans2*ans2*n;  
    }
    
    return ans2*ans2;
    }
    int pow(int a,int b){
        if(b==0){
            return 1;
        }
        return a*pow(a,b-1);
    }
  
}
```

#### Solution 2 (Java)

- **Submitted:** 2026-04-21 11:05:20
- **Status:** Correct
- **Marks:** 4

```java
class Solution {
    public int reverseExponentiation(int n) {
        // code here
       int val=0; 
       int ans=0;
       int num=n;
    while(num>0){
      val=num%10;
      num=num/10;
      ans=ans*10+val;
    }
    return pow(n,ans);
    }
    int pow(int a,int b){
        if(b==0){
            return 1;
        }
        return a*pow(a,b-1);
    }
  
}
```

*Generated on: 24/11/2026, 04:59:52*