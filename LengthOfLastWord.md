### Question
https://leetcode.com/problems/length-of-last-word/

### Solution
```JAVA
class Solution {
    public int lengthOfLastWord(String s) {
        s = s.trim();
    
        int lastSpaceIndex = s.lastIndexOf(" ") + 1;
        String result = s.substring(lastSpaceIndex , s.length());
		
        return result.length();
    }
}
```
