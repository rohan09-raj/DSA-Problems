### Question
https://leetcode.com/problems/word-pattern

### Solution
```JAVA
class Solution {
    public boolean wordPattern(String pattern, String s) {
        HashMap<Character, String> map = new HashMap<>();
        String[] words = s.split("\\s"); 
        
        if(words.length != pattern.length()) return false;
        
        for(int i=0; i<pattern.length(); i++) {
            if(map.containsKey(pattern.charAt(i))) {
                if(!map.get(pattern.charAt(i)).equals(words[i])) {
                    return false;
                }
            } else {
                if(map.containsValue(words[i])) {
                    return false;
                }
                
                map.put(pattern.charAt(i), words[i]);
            }
        }    
        return true;
    }
}
```
