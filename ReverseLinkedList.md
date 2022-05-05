### Question
https://leetcode.com/problems/reverse-linked-list

### Solution
```JAVA
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode reverseList(ListNode head) {
        // Iterative
        ListNode current = head;
        ListNode prev = null;
        
        while(current != null) {
            ListNode temp = current.next;
            current.next = prev;
            prev = current;
            current = temp;
        }
        
        return prev;
        
        // Recursive
        
        if(head == null || head.next == null) {
            return head;
        }
        
        ListNode newNode = reverseList(head.next);
        ListNode headNext = head.next;
        head.next = null;
        headNext.next = head;
        
        return newNode;
    }
}
```
