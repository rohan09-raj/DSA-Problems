### Question


### Solution
```JAVA
class Solution {
    public String addStrings(String num1, String num2) {
        String result = "";
        int sum = 0;
        int length1 = num1.length() - 1;
        int length2 = num2.length() - 1;
        
        while(length1 >= 0 || length2 >= 0) {
            if(length1 >= 0 && length2 >= 0) {
                sum += (num1.charAt(length1--) - '0') + (num2.charAt(length2--) - '0');
            } else if (length2 >= 0) {
                sum += (num2.charAt(length2--) - '0');
            } else {
                sum += (num1.charAt(length1--) - '0');
            }  
            result = sum % 10 + result;
            sum /= 10;
        }
        
        if(sum != 0) {
            result = sum + result;
        }    
        return result;
    }
}
```
