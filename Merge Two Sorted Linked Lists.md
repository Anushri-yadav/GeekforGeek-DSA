## 01. Merge Two Sorted Linked Lists

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/merge-two-sorted-linked-lists/1)

### Problem Description

**Task:** Given the head of two sorted linked lists consisting of nodes respectively. Merge both lists and return the head of the sorted merged list.Examples:Input: Output: 2 - > 3 - > 5 - > 10 - > 15 - > 20 - > 40

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n + m)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-05-30 11:22:55
- **Status:** Correct
- **Marks:** 4

```java
/*
class Node
{
    int data;
    Node next;
    Node(int d) {
        data = d;
        next = null;
    }
}
*/

class Solution {
    Node sortedMerge(Node head1, Node head2) {
        // code here
     Node i= head1;
     Node j= head2;
     Node k=new Node(0);
     Node head=k;
     while(i!=null && j!=null){
     if(i.data<j.data){
        k.next=i;
        k=i;
        i=i.next;
     }
        else{
            k.next=j;
            k=j;
            j=j.next;
        }
     }
      if(i!=null)   k.next=i;
      if(j!=null)   k.next=j;
     head=head.next;
    return head;
    }
}
```

*Generated on: 24/11/2026, 05:11:27*