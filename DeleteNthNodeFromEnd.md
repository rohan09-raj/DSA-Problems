### Question
https://leetcode.com/problems/remove-nth-node-from-end-of-list

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
    public ListNode removeNthFromEnd(ListNode head, int n) {
        if (head == null || head.next == null) {
            return null;
        }
        
        ListNode tempHead = head;
        int size = sizeOfList(tempHead);
        int kthNode = size-n;
        
        ListNode curr = head;
        int i = 1;
        
        while (i < kthNode) {
            curr = curr.next; 
            i++;
        }
        
        if (n == size) {
            return head.next;
        }
        
        curr.next = curr.next.next; 
        
        return head;
    }
    
    public int sizeOfList(ListNode head) {        
        int size = 0;
        
        while(head != null) {
            head = head.next;
            size++;
        }
        
        return size;
    }
}
```

### Wrong Approach
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
    public ListNode removeNthFromEnd(ListNode head, int n) {
        if (head.next == null || head == null) {
            return null;
        }

        ListNode revHead = reverse(head);
        ListNode deleteNode = revHead;
        
        int count = 1;
        
        if (n == 1) {           
            revHead = revHead.next;
            deleteNode.next = null;
            return reverse(revHead);
        }
        
        while (n < count) {
            deleteNode = deleteNode.next;
            count++;
        }
        
        deleteNode.next = deleteNode.next.next;
        
        return reverse(revHead);
    }
    
    public ListNode reverse(ListNode head) {
        ListNode prev = null;
        ListNode curr = head;
        
        while(curr != null) {
            ListNode currNext = curr.next;
            curr.next = prev;
            prev = curr;
            curr = currNext;
        }
        
        return prev;
    }
}
```
