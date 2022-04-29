### Question
https://leetcode.com/problems/word-pattern

### Solution
```JAVA
class Solution {
    public boolean wordPattern(String pattern, String s) {
        HashMap<Character,String> map = new HashMap<Character,String>();
        String str[]=s.split("\\s");
        
        if(str.length == pattern.length()) {
             for(int i=0; i<pattern.length(); i++) {
                if(!map.containsKey(pattern.charAt(i))) {
                    if(!map.containsValue(str[i])) {
                         map.put(pattern.charAt(i),str[i]);
                    } else {
                        return false;
                    } 
                } else {
                    if(!map.get(pattern.charAt(i)).equals(str[i])) {
                        return false;
                    }
                }
             }
            
             return true;
        } else {
            return false; 
        }
    }
}
```
