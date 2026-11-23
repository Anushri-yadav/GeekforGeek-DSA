## 01. Armstrong Numbers

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/armstrong-numbers2727/1)

### Problem Description

**Task:** Given a positive integer n, determine whether it is an Armstrong number or not.An Armstrong number is a number where, sum of each digit raised to the power digit count, is equal to the original number.Examples:Input: n = 153

#### Examples

##### Example 1

- **Output:**
```text
true
```
- **Explanation:** 1³ + 5³ + 3³ = 153, which is equal to the original number.

##### Example 2

- **Input:**
```text
n = 1634Output: true
```
- **Output:**
```text
false
```
- **Explanation:** 1³ + 0³ + 0³ = 1, which is not equal to 100.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(d), where d is the number of digits in nAuxiliary Space: O(d)
- **Expected Auxiliary Space Complexity:** O(d)

### Accepted Solutions (2)

#### Solution 1 (Java)

- **Submitted:** 2026-03-23 01:46:29
- **Status:** Correct
- **Marks:** 0

```java
// User function Template for Java
class Solution {
    static boolean armstrongNumber(int n) {
        // code here
        int num=n;
        int sum=0;
        while(num>0){
            int v=num%10;
            sum=sum+v*v*v;
            num=num/10;
        }
        if(sum==n){
            return true;
        }
        return false;
    }
}
```

#### Solution 2 (Java)

- **Submitted:** 2026-03-23 01:46:01
- **Status:** Correct
- **Marks:** 2

```java
// User function Template for Java
class Solution {
    static boolean armstrongNumber(int n) {
        // code here
        int num=n;
        int sum=0;
        while(num>0){
            int v=num%10;
            sum=sum+v*v*v;
            num=num/10;
        }
        if(sum==n){
            return true;
        }
        return false;
    }
}
```

*Generated on: 24/11/2026, 04:58:15*