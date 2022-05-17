### Question
https://leetcode.com/problems/ransom-note/

### Solution
```JAVA
class Solution {
    public boolean canConstruct(String ransomNote, String magazine) {
        int[] frequency = new int[26];
        
        for(int i=0; i<magazine.length(); i++) {
            frequency[magazine.charAt(i) - 'a']++;
        }
        
        for(int i=0; i<ransomNote.length(); i++) {
            if(frequency[ransomNote.charAt(i) - 'a'] != 0) {
                frequency[ransomNote.charAt(i) - 'a']--;
            } else {
                return false;
            }
        }
        
        return true;
    }
}
```
