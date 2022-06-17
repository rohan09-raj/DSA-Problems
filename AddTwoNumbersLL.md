### Question
https://leetcode.com/problems/add-two-numbers

### Solution
```JAVA
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode result = new ListNode();
        ListNode curr = result;
        int carry = 0;
        
        while(l1 != null || l2 != null || carry != 0) {
            int first = l1 != null ? l1.val : 0;
            int second = l2 != null ? l2.val : 0;

            int sum = carry + first + second;
            carry = (int) Math.floor(sum / 10);
            curr.next = new ListNode(sum % 10);
            curr = curr.next;                    

            if (l1 != null) l1 = l1.next;
            if (l2 != null) l2 = l2.next;
        }
        return result.next;
    }
}
```

**More Lines of Code Approach**
```JAVA
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        if(l1 == null) {
            return l2;
        }
        
        if(l2 == null) {
            return l1;
        }
        
        ListNode result = new ListNode();
        ListNode pointerNode = result;
        int carry = 0;
        int pointer = 0;
        
        while(l1 != null || l2 != null) {
            
            if(pointer != 0) {
                pointerNode.next = new ListNode();
                pointerNode = pointerNode.next;
            }
            
            if(l1 != null && l2 != null) {
                pointerNode.val = (l1.val + l2.val + carry) % 10;
                carry = (l1.val + l2.val + carry)/10;
                l1 = l1.next;
                l2 = l2.next;
            } else if (l2 != null) {
                pointerNode.val = (l2.val + carry) % 10;
                carry = (l2.val + carry) / 10;
                l2 = l2.next;
            } else {
                pointerNode.val = (l1.val + carry) % 10;
                carry = (l1.val + carry) / 10;
                l1 = l1.next;
            }
            
            pointer++;
        }
        
        if(carry != 0) {
            pointerNode.next = new ListNode();
            pointerNode = pointerNode.next;
            pointerNode.val = carry;
        }
        
        return result;
    }
}
```
