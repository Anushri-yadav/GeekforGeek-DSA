## 01. Delete Middle of Linked List

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/delete-middle-of-linked-list/1)

### Problem Description

**Task:** Given a singly linked list, delete the middle of the linked list.
If there are even nodes, then there would be two middle nodes, we need to delete the second middle element.
If the input linked list has a single node, then it should return NULL.

#### Examples

##### Example 1

- **Input:**
```text
LinkedList: 1- > 2- > 3- > 4- > 5
```
- **Output:**
```text
1- > 2- > 4- > 5Explanation:
```

##### Example 2

- **Input:**
```text
LinkedList: 2- > 4- > 6- > 7- > 5- > 1
```
- **Output:**
```text
2- > 4- > 6- > 5- > 1Explaination:
```

##### Example 3

- **Input:**
```text
LinkedList: 7 Output: < empty linked list > Explanation: There was only one node and it was deleted.
```

#### Constraints

- **1.** `1 <= number of nodes <= 10⁵`
- **2.** `1 <= node- > data <= 10⁹`

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-05-24 23:44:45
- **Status:** Correct
- **Marks:** 2

```java
/*
class Node {
    int data;
    Node next;
    Node(int d)  { data = d;  next = null; }
}
*/

class Solution {
    Node deleteMid(Node head) {
        // This is method only submission.
        // You only need to complete the method.
        Node s=head;
        Node s1=head;
        Node f=head;
       if(f==null) return head;
        if(f.next==null) return head.next;
        while(f!=null && f.next!=null){
            s1=s;
            s=s.next;
            f=f.next.next;
        }
        s1.next=s1.next.next;
        return head;
    }
}
```

*Generated on: 24/11/2026, 05:10:27*