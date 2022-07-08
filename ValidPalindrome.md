### Question
https://leetcode.com/problems/valid-palindrome

### Solution
**Correct Solution**
```JAVA
class Solution {
    public boolean isPalindrome(String s) {
        s = s.replaceAll("[^a-zA-Z0-9]", "");
        s = s.toLowerCase();
        
        int i = 0;
        int j = s.length() - 1;
        
        while(i<j) {
            if(s.charAt(i) != s.charAt(j)) {
                return false;
            }
            
            i++;
            j--;
        }
        
        return true;
    }
}
```
**Wrong Solution**
```JAVA
class Solution {
    public boolean isPalindrome(String s) {
        s.toLowerCase();
        
        StringBuilder res = new StringBuilder();
        
        for(int i=0; i<s.length(); i++) {
            if(s.charAt(i) >= 97 && s.charAt(i) <= 122) {
                res.append(s.charAt(i));
            }
        }
        
        if(res.reverse() == res) {
            return true;
        }
        
        return false;
    }
}
```
