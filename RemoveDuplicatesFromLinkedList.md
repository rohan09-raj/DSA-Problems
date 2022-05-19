### Question
https://leetcode.com/problems/remove-duplicates-from-sorted-list/

### Solution
```JAVA
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        ListNode current = head;
        
        while(current != null && current.next != null) {
            ListNode next = current.next;
            
            if(next.val != current.val) {
                current = next;
            } else {
                current.next = current.next.next;
            }
        }
        
        return head;
    }
}
```
