### Question
https://leetcode.com/problems/plus-one/

### Solution
```JAVA
class Solution {
    public int[] plusOne(int[] digits) {
        int size = digits.length;
        for (int i = size - 1; i >= 0; i--) {
            if (digits[i] == 9) {
                digits[i] = 0;
            } else {
                digits[i] += 1;
                break;
            }
        }
        
        if(digits[0] != 0) {
            return digits;
        };
        
        int[] res = new int[size + 1];
        res[0] = 1;
        return res; 
    } 
}
```
