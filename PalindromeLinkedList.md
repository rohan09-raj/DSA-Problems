### Question
https://leetcode.com/problems/palindrome-linked-list/

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
    public boolean isPalindrome(ListNode head) {
        if (head == null) {
            return true;
        }
        
        ListNode middle = middle(head);
        ListNode revHead = reverse(middle.next);
        ListNode currHead = head;
        
        while(revHead != null) {
            if (revHead.val != currHead.val) {
                return false;
            }
            
            revHead = revHead.next;
            currHead = currHead.next;
        } 
        
        return true;
    }
    
    public ListNode middle(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;
        
        while (fast != null && fast.next != null) {
            fast = fast.next.next;
            slow = slow.next;
        }
        
        return slow;
    }
    
    public ListNode reverse(ListNode node) {
        ListNode current = node;
        ListNode prev = null;
        
        while(current != null) {
            ListNode temp = current.next;
            current.next = prev;
            prev = current;
            current = temp;
        }
        
        return prev;
    }
    
}
```
