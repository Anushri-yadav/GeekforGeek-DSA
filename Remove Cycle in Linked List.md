## 01. Remove Cycle in Linked List

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/remove-loop-in-linked-list/1)

### Problem Description

**Task:** Given the head of a singly linked list. A cycle exists if the last node points back to a previous node, forming a loop. Remove the loop from the linked list if it exists.Internally, the driver code uses a variable x (1-based indexing) to represent the position of the node to which the last node is connected.The driver code will print "true" if the linked list is correctly modified, otherwise it will print "false".Examples:Input:Output: true

#### Examples

##### Example 1

- **Output:**
```text
true
```
- **Explanation:** The linked list contains a loop that begins at node x = 1. After removing the loop, the driver code prints true.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-05-29 18:31:52
- **Status:** Correct
- **Marks:** 4

```java
class Solution {
    public static boolean removeLoop(Node head) {
        Node slow = head, fast = head;

        // Step 1: Detect Loop
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;

            if (slow == fast) {  
                removeCycle(head, slow);
                return true;
            }
        }

        return true; // as per expected output
    }

    private static void removeCycle(Node head, Node meet) {
        Node p1 = head, p2 = meet;

        // If loop starts at head
        if (p1 == p2) {
            while (p2.next != p1)
                p2 = p2.next;
            p2.next = null;
            return;
        }

        // Normal case
        while (p1.next != p2.next) {
            p1 = p1.next;
            p2 = p2.next;
        }
        p2.next = null;
    }
}
```

*Generated on: 24/11/2026, 05:09:54*