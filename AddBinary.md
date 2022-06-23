### Question
https://leetcode.com/problems/add-binary/

### Solution
```JAVA
class Solution {
    public String addBinary(String a, String b) {
        StringBuilder res = new StringBuilder();   
        
        int carry = 0;
        
        int aP = a.length() - 1;
        int bP = b.length() - 1;
        
        while(aP >= 0 || bP >= 0) {
            int sum = carry;
            
            if(aP >= 0) sum = sum + a.charAt(aP--) - '0';
            if(bP >= 0) sum = sum + b.charAt(bP--) - '0';
            
            res.append(sum % 2);
            carry = sum / 2;
        }
        
        if (carry != 0) {
            res.append(carry);
        }
        
        return res.reverse().toString();
    }
}
```
