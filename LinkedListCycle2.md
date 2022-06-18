### Question
https://leetcode.com/problems/linked-list-cycle-ii

### Solution
**Short approach**
```JAVA
public class Solution {
    public ListNode detectCycle(ListNode head) {
        Set<ListNode> set = new HashSet<>();
        
        while(head != null) {
            if(set.contains(head)) {
                return head;
            }
            set.add(head);
            head=head.next;
        }
        return null;
    }
}
```

**Long approach**
```JAVA
public class Solution {
    public ListNode detectCycle(ListNode head) {
        if (head == null || head.next == null) {
            return null;
        }
        
        ListNode fast = head;
        ListNode slow = head;
        
        ListNode result = null;
        
        while(fast != null && fast.next != null) {
            fast = fast.next.next;
            slow = slow.next;
            
            if(slow == fast) {
                result = slow;
                break;
            }
        }
        
        if(result == null) return null;
        
        ListNode dummy = head;
        while(dummy != result) {
            dummy = dummy.next;
            result = result.next;
        }
        
        return dummy;
    }
}
```
